# arm64-hosted-runner
Repository to run the recent Linux arm64 hosted runner service.

The workflow is defined in the file: https://github.com/djerry96/arm64-hosted-runner/blob/main/.github/workflows/auto_stream_distro.yml

The repository to pull the manifests is located in: https://github.com/djerry96/AutoSD-ImageBuider-Manifests






Command to run in QEMU the ARM image for the Automotive Kernel from the SIG AutoSD.
  
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
