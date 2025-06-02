```bash
#!/bin/bash

echo "configure build output path"

KERNEL_TOP_PATH="$( cd "$(dirname "$0")" ; pwd -P)" 
OUTPUT="$KERNEL_TOP_PATH/out"
echo "$OUTPUT"

KERNEL=kernel8

cd out

make O=$OUTPUT modules_install #모듈 인스톨
cp $OUTPUT/arch/arm64/boot/dts/broadcom/*.dtb /boot/ # boot에 카피
cp $OUTPUT/arch/arm64/boot/dts/overlays/*.dtb* /boot/overlays/ #overlays 특수한 기능 에 대체 
#cp $OUTPUT/arch/arm64/boot/dtts/overlays/README /boot/overlays/
cp $OUTPUT/arch/arm64/boot/Image /boot/$KERNEL.img
# 커널의 Image 파일을  kernal.img로 바꿔서 복사한다.. 
```