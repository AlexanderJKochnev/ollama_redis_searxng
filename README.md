# ollama_redis_searxng НИ В КОЕМ СЛУЧАЕ НЕ ОБНОВЛТЬ DEBIAN - драйвера NVIDIA не успевают за debian 13
ollama + redis + searxng
переустановка драйверов NVIDIA (если обновил все таки debian 13)

1. sudo apt update
2. sudo apt install linux-headers-$(uname -r) dkms -y
3. sudo apt install nvidia-driver nvidia-cuda-toolkit -y
4. sudo apt install linux-headers-amd64 linux-headers-$(uname -r)
5. sudo /usr/sbin/dkms status
6. dpkg -l | grep nvidia-kernel-dkms
   1. ii  nvidia-kernel-dkms                   **550.163.01-2**                         amd64        NVIDIA binary kernel module DKMS source
7. sudo /usr/sbin/dkms install -m nvidia-current -v 550.163.01 -k $(uname -r)
8. sudo modprobe nvidia
9. nvidia-smi

## где лежат модели
/mnt/hdd_data/volumes/wine_ollama_data
 
