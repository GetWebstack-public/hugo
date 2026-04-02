# hugo

A static site example built with [Hugo](https://gohugo.io/) — a fast and flexible open-source static site generator written in Go.

## Run with gws

### 1. Install the GetWebstack CLI

Install the [GetWebstack](https://getwebstack.com) CLI ([docs](https://getwebstack.com/docs) | [installation](https://getwebstack.com/docs/installation)):

```bash
curl -sSL https://getwebstack.com/install.sh | bash
```

### 2. Clone the repository

```bash
git clone https://github.com/GetWebstack-public/hugo
cd hugo
```

### 3. Initialise from template setup

```bash
gws init --from-file gws.json
```

### 4. Deploy the service

```bash
gws up
```

### 5. Stream logs

```bash
gws logs
```

### 6. See deployment status

```bash
gws status
```
