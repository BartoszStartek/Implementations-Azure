Na początku rozwiązania stoi Traffic Manager, którego metodą routingu ruchu jest Priority.<br/>
Priorytet 1 to publiczy adres IP Load Balancera, który następnie rozrzuca ruch pomiedzy dwoma wirtualnymi maszynami Ubuntu z zaistalowanym Apache serverem.<br/>
Priorytet 2 to Azure WebApp. Jak nie dzialają maszyny lub Load Balancer to automatycznie ruch idzie na WebApp.

Zastosowane usługi: Traffic Manager, Load Balancer, 2VMs+Apache Server, WebApp.
