docker save cypress/win-cli:latest -o  cypress.tar
split -b 50M cypress.tar cypress_
