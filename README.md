# hen2to3 migrationsteps

1) Download Helm Binary tar file from the repo ( Depends upon the operating system) 

   https://github.com/helm/helm/releases
   
2) Unzip and move the helm file to /usr/local/bin as helm3 ( You will have the file as /usr/local/bin/helm3)

3) Install the helm 2to3 plugin using helm 
   command: helm3 plugin install https://github.com/helm/helm-2to3
   
4) verify using command: helm plugin list

5) you can see all possible options using command:  helm3 2to3 --help 

6) Move the config from helm to helm3 on local using the command: helm3 2to3 move config ( Use dry run before doing teh actual)

7) Convert the deployments from helm version 2 to helm version 3 using command: helm 2to3 convert <deployment name> ( Can try the dry run )
  
8) Clean up using : helm3 2to3 cleanup ( Removes the tiller and deletes the helm version2 deployments )

9) Then rename the helm3 as helm under /usr/local/bin

10) Then we can use helm uninstall <deployment> command  (Instead of using helm delete --purge)
   
11) in helm install command instead of --name , go with just name  (helm install --upgrade <deployment> name <name of the release>

