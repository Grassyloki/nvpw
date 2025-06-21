# nvpw - NVIDIA Power Wrapper

Simple power management for NVIDIA GPUs on Arch Linux laptops with hybrid graphics.

## Requirements

- Arch Linux
- Laptop with integrated GPU + NVIDIA dedicated GPU  
- nvidia-utils package (`sudo pacman -S nvidia-utils`)
- sudo access

## Installation

1. Create the main script:
```bash
sudo vim /usr/local/bin/nvpw
```
Copy the nvpw script content, save and exit (`:wq`)

2. Make it executable:
```bash
sudo chmod +x /usr/local/bin/nvpw
```

3. (Optional) Auto-disable GPU at boot:
```bash
sudo vim /etc/systemd/system/gpu-off.service
```
Copy the systemd service content, save and exit (`:wq`)

```bash
sudo systemctl enable gpu-off.service
```

## Usage

```bash
nvpw        # Show help and current GPU status
nvpw on     # Turn GPU on
nvpw off    # Turn GPU off
```

## Notes

- Default GPU address is `0000:01:00.0` - edit the script if yours differs
- Check your GPU address with: `lspci | grep -i nvidia`
