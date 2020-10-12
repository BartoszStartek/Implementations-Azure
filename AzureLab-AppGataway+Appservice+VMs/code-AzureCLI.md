rg=rg-appgwtest


<b>az group create</b> --name $rg --location west europe


<b>az network vnet create</b>  --resource-group $rg  --name vehicleAppVnet  --address-prefix 10.0.0.0/16  --subnet-name webServerSubnet --subnet-prefix 10.0.1.0/24

<b>git clone</b> https://github.com/MicrosoftDocs/mslearn-load-balance-web-traffic-with-application-gateway module-files


<b>az vm create</b> --resource-group appgwtest --name webServer1 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys --vnet-name vehicleAppVnet --subnet webServerSubnet --custom-data module-files/scripts/vmconfig.sh --no-wait

<b>az vm create</b> --resource-group appgwtest --name webServer2 --image UbuntuLTS --admin-username azureuser --generate-ssh-keys --vnet-name vehicleAppVnet --subnet webServerSubnet --custom-data module-files/scripts/vmconfig.sh

<b>az vm list</b> --resource-group appgwtest --show-details --output table


<b>az appservice plan create</b> --resource-group appgwtest --name vehicleAppServicePlan --sku S1


<b>az webapp create</b> --resource-group appgwtest --name myowntestappbs123 --plan vehicleAppServicePlan --deployment-source-url https://github.com/MicrosoftDocs/mslearn-load-balance-web-traffic-with-application-gateway --deployment-source-branch appService


<b>az network vnet subnet create</b> --resource-group appgwtest --vnet-name vehicleAppVnet  --name appGatewaySubnet --address-prefixes 10.0.0.0/24

<b>az network public-ip create</b> --resource-group appgwtest --name appGatewayPublicIp --sku Standard --dns-name myowntestappbs123-dns


<b>az network application-gateway create</b> --resource-group appgwtest --name vehicleAppGateway --sku WAF_v2 --capacity 2 --vnet-name vehicleAppVnet --subnet appGatewaySubnet --public-ip-address appGatewayPublicIp --http-settings-protocol http --http-settings-port 8080 --frontend-port 8080


<b>az network application-gateway address-pool create</b> --gateway-name vehicleAppGateway --resource-group appgwtest --name vmPool --servers 13.93.117.24 52.178.8.176


<b>az network application-gateway address-pool create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name appServicePool --servers myowntestappbs123.azurewebsites.net


<b>az network application-gateway frontend-port create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name port80 --port 80

<b>az network application-gateway http-listener create</b> --resource-group appgwtest --name vehicleListener --frontend-port port80 --gateway-name vehicleAppGateway


<b>az network application-gateway probe create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name customProbe --path / --interval 15 --threshold 3 --timeout 10 --protocol Http --host-name-from-http-settings true

<b>az network application-gateway http-settings update</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name appGatewayBackendHttpSettings --host-name-from-backend-pool true --port 80 --probe customProbe


<b>az network application-gateway url-path-map create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name urlPathMap --paths /VehicleRegistration/* --http-settings appGatewayBackendHttpSettings --address-pool vmPool

<b>az network application-gateway url-path-map rule create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name appServiceUrlPathMap --paths /LicenseRenewal/* --http-settings appGatewayBackendHttpSettings --address-pool appServicePool --path-map-name urlPathMap


<b>az network application-gateway rule create</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name appServiceRule --http-listener vehicleListener --rule-type PathBasedRouting --address-pool appServicePool --url-path-map urlPathMap


<b>az network application-gateway rule delete</b> --resource-group appgwtest --gateway-name vehicleAppGateway --name rule1


<b>az network public-ip show</b> --resource-group appgwtest --name appGatewayPublicIp --query dnsSettings.fqdn --output tsv
