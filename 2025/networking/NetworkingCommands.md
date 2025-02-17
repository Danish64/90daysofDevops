**Network Commands Cheat Sheet for DevOps Engineers**

### 1. **ping** – Check Connectivity

**Purpose:** Tests if a remote host is reachable and measures response time.  
**Syntax:**

```sh
ping google.com
```

**Common Flags:**

- `-c <count>`: Stop after sending <count> packets.
- `-i <interval>`: Set interval between packet transmissions.
- `-t <ttl>`: Set time-to-live for packets.

**Real-World Use Case:**
A DevOps engineer uses `ping` to check if a server is online before deploying updates.

---

### 2. **traceroute** – Trace Packet Route

**Purpose:** Displays the path packets take to reach a destination.  
**Syntax:**

```sh
traceroute google.com
```

**Common Flags:**

- `-m <max_hops>`: Set maximum number of hops.
- `-q <nqueries>`: Set the number of probe packets per hop.

**Real-World Use Case:**
Used to diagnose slow connections by identifying problematic network hops.

---

### 3. **netstat** – Network Statistics

**Purpose:** Shows active network connections, listening ports, and routing tables.  
**Syntax:**

```sh
netstat -an
```

**Common Flags:**

- `-t`: Show TCP connections.
- `-u`: Show UDP connections.
- `-p`: Show process ID of owning connection.

**Real-World Use Case:**
Used to check if an application is properly listening on a port before exposing it in a production environment.

---

### 4. **curl** – Make HTTP Requests

**Purpose:** Sends HTTP requests to test API endpoints.  
**Common CRUD Syntax:**

- **GET (Retrieve Data)**
  ```sh
  curl -X GET https://jsonplaceholder.typicode.com/posts/1
  ```
- **POST (Create Data)**
  ```sh
  curl -X POST https://jsonplaceholder.typicode.com/posts \
       -H "Content-Type: application/json" \
       -d '{"title": "New Post", "body": "Content here", "userId": 1}'
  ```
- **PUT (Update Data)**
  ```sh
  curl -X PUT https://jsonplaceholder.typicode.com/posts/1 \
       -H "Content-Type: application/json" \
       -d '{"title": "Updated Title", "body": "Updated content", "userId": 1}'
  ```
- **DELETE (Remove Data)**
  ```sh
  curl -X DELETE https://jsonplaceholder.typicode.com/posts/1
  ```

**Common Flags:**

- `-X <method>`: Specify HTTP method (GET, POST, PUT, DELETE).
- `-H <header>`: Add a request header.
- `-d <data>`: Send data in the request body.
- `-v`: Enable verbose mode to debug requests.

**Real-World Use Case:**
Used to verify if a microservice API is responding correctly after deployment.

---

### 5. **dig** – DNS Lookup

**Purpose:** Queries DNS records for a domain.  
**Syntax:**

```sh
dig google.com
```

**Common Flags:**

- `+short`: Display a concise output.
- `+trace`: Show the full resolution path.
- `@<dns_server>`: Query a specific DNS server.

**Real-World Use Case:**
Used to verify if a DNS change has propagated after updating a domain’s DNS settings.

---

### 6. **nslookup** – Query DNS Records

**Purpose:** Retrieves DNS information for a domain.  
**Syntax:**

```sh
nslookup google.com
```

**Common Flags:**

- `-type=<record_type>`: Query a specific record type (A, MX, TXT, etc.).
- `<server>`: Specify a DNS server to use.

**Real-World Use Case:**
Used to troubleshoot domain resolution issues when a website is not loading.
