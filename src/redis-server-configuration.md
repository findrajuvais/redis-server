# Redis Server Configuration:

### Download `redis-stable.tar.gz` file:
```bash
wget http://download.redis.io/redis-stable.tar.gz
```
#### OR:
```bash
curl -O http://download.redis.io/redis-stable.tar.gz
```

### After download unzip `redis-stable.tar.gz` file:
```bash
tar -xzvf redis-stable.tar.gz
```

### Go into redis-stable folder:
```bash
cd redis-stable
```

### Run command for configuration:
```bash
sudo make install
#OR
make
```
### Copy `redis.conf` file to `/etc/redis.conf`
```bash
cp redis.conf /etc/redis.conf
```

### Open `/etc/redis.conf` file:
```bash
vi /etc/redis.conf
```

### Run command to make redis server ready:
```bash
src/redis-server /etc/redis.conf
```

### Check redis server:
```bash
src/redis-cli ping

# grep redis is running or not
ps aux | grep redis

# Check with command
redis-cli -h 127.0.0.1 -p 6379 ping
```

### Set Password:
```bash
vi /etc/redis.conf

### After open file uncomment this parameter

requirepass my_secure_password # Pass@123
```

### Set Specific IP:
```bash
bind x.x.x.1 # instead of 127.0.0.1 or 0.0.0.0

# Check redis is running or not if running stop that
ps aux | grep redis
kill -i <PID>

# Run this command after kill to restart
src/redis-server /etc/redis.conf

# Now Check
redis-cli -h x.x.x.1 -p 6379 -a Pass@123 ping
```

###### [All process done]

#### Next:


