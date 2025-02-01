(*Install Go from Official Tarball* **(this is Recommended)**)

### 1. Remove Old version of Go installed if any (if any)
```bash
sudo rm -rf /usr/local/go

```

### 2. Download the Latest Go version
First, check the latest version from the official [Go downloads page](https://go.dev/). Then, run:
```bash
curl -OL https://go.dev/dl/go1.22.0.linux-amd64.tar.gz
```

### 3.Extract and Install
```bash
sudo tar -C /usr/local -xzf go1.22.0.linux-amd64.tar.gz
```

### 4. Set Up Environments Variables
Add Go to your system path by updating `~/.bashrc` or `~/.profile`:
```bash
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
source ~/.bashrc
```

### 5. Verify Installation
```bash 
go version
```


***If everything is correct, it should show the latest version.***