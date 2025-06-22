## Installing Docker Using the Official Script

For robotics development, we often want a quick and reliable way to install Docker. One of the easiest approaches is to use Docker’s official installation script. Below are the detailed steps and explanations, along with potential pitfalls and how to address them.

---

### 1️⃣ Download the official Docker installation script

We’ll use `curl` to fetch the installation script provided by Docker:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
```

### 2️⃣ (Optional) Perform a dry run to see what the script will do
It’s a good practice to check what the script will execute:

```bash
sudo sh ./get-docker.sh --dry-run
```

### 3️⃣ Run the script to install Docker
Once you’re satisfied with the dry run, proceed with the installation:

```bash
sudo sh ./get-docker.sh
```

### 4️⃣ Verify the installation
Check the installed Docker version:

```bash 
docker --version
```



### 5️⃣ Add your user to the docker group
By default, Docker commands require sudo. To allow your user to run Docker without sudo, do:

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```


### 6️⃣ Enable Docker to start on boot
Set Docker and containerd to start automatically when your system boots:

```bash
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```


### (Optional) Diable Dcker to start on boot
Set Docker and containerd to not start automatically when your system boots:

```bash
sudo systemctl disable docker.service
sudo systemctl disable containerd.service
```

### References: 
- [Docker install script documentation](https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script)
- [Post-install steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/)
