https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13

Azure Set up for CICD
https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13&pp=iAQB
Find Container Registry → Registry Name + Resource group → testdockerifte.azurecr.io (keeping docker image) 
After Creation → go to resource → Access Keys → enable admin user → keep remember 
Login server/password
Create Webapp → Instance Name (mltestifte) → Resource testdockerifte → publish container (default value code)
Go to Container Tab → Azure container registry → Image (Need to create from Local machine) → after the following step Image name should be in drop down list

Run from terminal:
# docker build -t testdockerifte.azurecr.io/mltestifte:latest .
# docker login testdockerifte.azurecr.io → here password is only the testdockerifte from testdockerifte.azurecr.io
# docker push testdockerifte.azurecr.io/mltestifte:latest  → if there is any login issues then install azure cli → run the following commands in cmd
az login
az acr login --name testdockerifte
Then Try again 
Webapp → deployment center → source (Github action build deploy ….. ) → provide repository infos → continuous deployment Turn it on 
