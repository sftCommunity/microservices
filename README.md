### Steps to Create Git Submodules

## Development

1. Clone the repository to your local machine
```
git clone https://github.com/sftCommunity/microservices.git
```
2. Initialize and update submodules when someone clones the repository for the first time, they must execute the following command to initialize and update the submodules
```
git submodule update --init --recursive
```
3. Add the submodule, where `repository_url` is the repository URL and `directory_name` is the folder name where you want to store the submodule (must not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add changes to the repository (git add, git commit, git push)
Example:
```
git add .
git commit -m "Add submodule"
git push
```
5. To update submodule references
```
git submodule update --remote
```

## Important
When working with a repository that has submodules, **first update and push** in the submodule and **then** in the main repository.

If done in reverse order, submodule references in the main repository will be lost, and you'll have to resolve conflicts.

## Production

execute command 
```
docker compose -f docker-compose.prod.yml build
```