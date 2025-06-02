```bash
#!/bin/bash

echo "configure build output path"

KERNEL_TOP_PATH="$( cd "$(dirname "$0")" ; pwd -P)" 
OUTPUT="$KERNEL_TOP_PATH/out"# 빌드할 위치 정하기
echo "$OUTPUT"

KERNEL=kernel8

cd out

make O=$OUTPUT modules_install #모듈 인스톨
cp $OUTPUT/arch/arm64/boot/dts/broadcom/*.dtb /boot/ # boot에 카피
cp $OUTPUT/arch/arm64/boot/dts/overlays/*.dtb* /boot/overlays/ #overlays 특수한 기능 에 대체 
#cp $OUTPUT/arch/arm64/boot/dtts/overlays/README /boot/overlays/
cp $OUTPUT/arch/arm64/boot/Image /boot/$KERNEL.img
# 커널의 Image 파일을  kernal8.img로 바꿔서 복사한다.. 
```

1. vmlinux: 이것은 컴파일된 후의 원본 리눅스 커널 이미지. 디버깅 정보와 기타 메타데이터를 포함할 수있기 때문에 파일크기가 큼
2. 