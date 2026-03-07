# Jon의 RMK 펌웨어

- [English](/README.md)
- [한국어](/README_KO.md)

이 저장소는 기존 ZMK 구성에서 RMK 기반 단일 멀티 타겟 펌웨어로 이전한 프로젝트입니다.

## V1 범위

- Keyboard: 모든 지원 키보드 패밀리 split 타겟
- Continuum: 공용 레이어/동작 canonical core
- Dongle: `basic`, `zdd`, `prospector`
- Scanner: `prospector_scanner` (v1은 non-touch observer)

지원 패밀리:

- `totem`
- `urchin`
- `corne`
- `eyelash_corne`
- `sofle`
- `eyelash_sofle`
- `delta_omega`
- `cornix`

## 저장소 구조

```text
rmk-firmware/
├── src/                         # central/peripheral/dongle/scanner/reset bin 엔트리
├── profiles/                    # 역할/패밀리별 RMK profile TOML
├── continuum/                   # core + matrix + generated
├── tools/generate_continuum_layers/         # Rust 기반 Continuum 생성기
├── Makefile.toml                # 전체 빌드 매트릭스
├── docs/
└── ZMK to RMK V1.md
```

## 빌드

필수:

1. Rust toolchain (`rust-toolchain.toml`)
2. `cargo-make`

```bash
cargo install --force cargo-make
```

주요 명령:

```bash
# 전체 task 목록
cargo make --list-all-steps

# 단일 타겟 빌드
cargo make build-totem_left --release

# 단일 타겟 uf2 생성
cargo make uf2-totem_left --release

# 전체 매트릭스 빌드
cargo make build-matrix --release

# 전체 매트릭스 uf2 생성
cargo make uf2 --release
```

## Continuum 작업 흐름

1. `continuum/core/layers.toml` 수정
2. `continuum/matrix/<family>.toml` 수정
3. 생성 스크립트 실행

```bash
cargo run --manifest-path tools/generate_continuum_layers/Cargo.toml --target host-tuple --release
```

생성 결과:

- `continuum/generated/*.toml`
- `profiles/keyboard/*.toml`의 `[layout]`

## 아티팩트/플래시

- 아티팩트 이름은 기존 호환 규칙을 유지합니다.
- 생성된 `.hex`/`.uf2`는 저장소 루트에 생성됩니다.
- 보드 부트로더 모드 진입 후 해당 `.uf2`를 복사해 플래시합니다.

공용 reset 아티팩트:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## 문서

- [V1 계획](./ZMK%20to%20RMK%20V1.md)
- [Target Inventory](./docs/V1_TARGET_INVENTORY.md)
- [Development](./docs/development.md)
- [Continuum](./docs/continuum.md)
- [Dongle](./docs/dongle.md)
- [Totem](./docs/totem.md)
- [Urchin](./docs/urchin.md)
- [Corne / Eyelash Corne](./docs/corne.md)
- [Sofle / Eyelash Sofle](./docs/sofle.md)
- [Delta Omega](./docs/delta_omega.md)
- [Cornix](./docs/cornix.md)

## 라이선스

이 저장소는 [MIT License](./LICENSE)를 따릅니다.
