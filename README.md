-- docker save image as tar
docker save cypress/win-cli:latest -o  cypress.tar
-- split into smaller chunks
split -b 50M cypress.tar cypress_
-- git commit changes
git add . && git commit -m "update" && git push
-- join chunks as tar
cat cypress_* > cypress.tar
-- load tar as docker image
docker load < cypress.tar
