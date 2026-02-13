# Sondiale
Prod sondiale.ma

## Local Development with Docker

### Prerequisites
- Docker and Docker Compose installed

### Initial Setup (First Time Only)

1. Copy the environment template file:
```bash
cp .env.example .env
```

2. Update the `.env` file with your user's ID and group ID:
```bash
# Get your UID and GID
id

# Update .env with the values (example if you get uid=1001(vbrevus) gid=1001(vbrevus))
# Edit .env and set:
UID=1001
GID=1001
```

### Running the Development Server

Start the Hugo development server:
```bash
docker-compose up
```

The site will be available at `http://localhost:1313`. The development server automatically reloads when you make changes to the content.

### Stopping the Server

```bash
docker-compose down
```

## Contributing

### Merge Strategy

- **Feature branch to main**: Squash and merge
- **Main to production**: Rebase merge

### Release Tags

When merging to production, create a release and tag on GitHub:

1. Go to the repository on GitHub
2. Click on "Releases" in the sidebar
3. Click "Create a new release"
4. Enter the version tag (e.g., `v1.0.0`)
5. Add release notes describing the changes
6. Publish the release

### Checking the Deployed Version

The currently deployed version on production can be checked by looking at the last `<div>` tag of the footer where
the `deployed_git_tag` variable is displayed, showing the current release version (e.g., `v1.0.0`). The last `<div>`
tag is hidden and can be checked by HTML inspection using browser developer tools.

---

### Resources

Hugo theme:
- [Demo Paige](https://bexer-hugo.vercel.app/)
- [Theme Bexer](https://gethugothemes.com/products/bexer)
- [Theme Bexer Documentation](https://docs.gethugothemes.com/bexer/)
- [Official Hugo Docker Image - GitHub registry](https://github.com/gohugoio/hugo/pkgs/container/hugo)
