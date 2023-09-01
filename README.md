## Bug in docker-compose up

### Docker compose 2.18.1 (no issue)

```bash
docker compose up --build --no-deps
```

```
[+] Running 3/2
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.1s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:37:04 UTC 2023
test  | Up & running at Fri Sep  1 09:37:11 UTC 2023
```

```bash
docker compose up --build --no-deps db test
```

```
[+] Running 3/1
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.0s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:37:24 UTC 2023
test  | Up & running at Fri Sep  1 09:37:31 UTC 2023
```

### Docker compose v2.19.1 (presents the issue)

```bash
docker compose up --build --no-deps
```

```
[+] Running 3/1
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.0s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:35:39 UTC 2023
test  | Up & running at Fri Sep  1 09:35:46 UTC 2023
```

```bash
docker compose up --build --no-deps db test
```

```
[+] Running 3/1
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container test              Created                                                                                                                                                                          0.0s
 ✔ Container db                Created                                                                                                                                                                          0.0s
Attaching to db, test
test  | Up & running at Fri Sep  1 09:36:04 UTC 2023
db    | Up & running at Fri Sep  1 09:36:04 UTC 2023
```

### Docker compose v2.20.3 (presents the issue)

```bash
docker compose up --build --no-deps
```

```
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.1s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:30:28 UTC 2023
test  | Up & running at Fri Sep  1 09:30:35 UTC 2023
```

```bash
docker compose up --build --no-deps db test
```

```
[+] Running 3/1
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.0s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:31:19 UTC 2023
test  | Up & running at Fri Sep  1 09:31:19 UTC 2023
```

### Docker compose v2.21.0 (presents the issue)

```bash
docker compose up --build --no-deps
```

```
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container db                Created                                                                                                                                                                          0.0s
 ✔ Container test              Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:33:23 UTC 2023
test  | Up & running at Fri Sep  1 09:33:30 UTC 2023
```

```bash
docker compose up --build --no-deps db test
```

```
[+] Running 3/1
 ✔ Network bug-dcp-up_default  Created                                                                                                                                                                          0.1s
 ✔ Container test              Created                                                                                                                                                                          0.0s
 ✔ Container db                Created                                                                                                                                                                          0.0s
Attaching to db, test
db    | Up & running at Fri Sep  1 09:34:18 UTC 2023
test  | Up & running at Fri Sep  1 09:34:18 UTC 2023
```
