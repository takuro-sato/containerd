## Use custom containerd in linux with docker installed

```bash
PREFIX=/usr sudo make install

# Assuming `disabled_plugins = ["cri"]` is the only difference from the default
# https://github.com/kubernetes/website/issues/33770
sudo rm -f /etc/containerd/config.toml

sudo systemctl kill containerd
sudo systemctl start containerd

docker run hello-world
```

