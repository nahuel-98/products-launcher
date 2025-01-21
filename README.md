## Start the whole microservices - Development environment
1. Clone the repository
2. Create a .env based on the .env.template.
3. Run the command `git submodule update --init --recursive`
4. Run the command `docker compose up --build`

### Steps to create Git Submodules

1. Create a new repository on GitHub
2. Clone the repository on the local machine
3. Add the submodule, where `repository_url` is the url of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (it should not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add the changes to the repository (git add, git commit, git push)
Ex:
```
git add .
git commit -m "Add submodule"
git push
```
5. Initialize and update submodules, when someone clones the repository for the first time, they must run the following command to initialize and update the submodules
```
git submodule update --init --recursive
```
6. To update the references of the submodules
```
git submodule update --remote
```

## Important
If you work in the repository that has the submodules (payment-ms for example), **first push the added changes** in that submodule and **then** in the main repository (root). That is, after updating and pushing in the submodule, it will be necessary to push a commit in the main repository updating the reference with the hash of the last commit of the submodule.

If done the other way around, the submodule references in the main repository will be lost and we will have to resolve conflicts.

## Architecture

![Image](https://github.com/user-attachments/assets/04a65ee4-d813-4c3c-9136-6914679a1aaf)