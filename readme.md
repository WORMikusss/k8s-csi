ceph fs subvolumegroup create cephfs csi
ceph fs subvolumegroup ls cephfs

Установка csi-драйверов cephfs и rbd для k8s:

CEPHFS:

Получаем ключ для пользователя admin на одной из нод ceph

ceph auth get-key client.admin

Монтирование на клиентских машинах:

apt install ceph-fuse

ceph-fuse -m 172.17.25.50:6789 /mnt/cephfs --id admin  -d --no-mon-config
