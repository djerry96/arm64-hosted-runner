# arm64-hosted-runner
Repository to test the recent Linux arm64 hosted runner service


  
qemu-system-aarch64 \
  -machine virt \
  -cpu cortex-a57 \
  -m 2048 \
  -nographic \
  -drive file=hosted_build_github_qemu.qcow2,if=virtio \
  -netdev user,id=net0 \
  -device virtio-net-device,netdev=net0 \
  -bios /usr/share/qemu-efi-aarch64/QEMU_EFI.fd \
  -boot c
