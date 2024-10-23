[🇬🇧 English](README.md) / [🇸🇪 Svenska](README_se.md) 
# Kubernetes Terminology
Denna ordlista definierar några av de vanligaste termerna som används i Kubernetes-världen.
<img width="200" alt="K8sLogo" src="https://github.com/kubernetes/kubernetes/blob/master/logo/logo.png" align=left>
<br>
<br>


[Kubernetes](https://kubernetes.io), även känt som K8s, är ett open-source-system för att automatisera distribution, skalning och hantering av containeriserade applikationer. Det grupperar containrar som utgör en applikation i logiska enheter för enkel hantering och upptäckt. Kubernetes bygger på 15 års erfarenhet av att köra produktionsarbetsbelastningar hos Google, kombinerat med de bästa idéerna och metoderna från gemenskapen (community).
<br>
<br>
<br>
<br>
<br>
<br>


| Termer | Definitioner |
| :- | :- |
|[Admission controller](#admission_controller) |Kod som validerar eller modifierar resurser för att upprätthålla policyer. Körs som en del av API-admission-kedjan direkt efter autentisering och auktorisering. |
|[Annotation](#annotation)|Metadata för objekt, ofta används för att exponera alfa- eller beta-funktioner, eller för att integrera med tredjepartssystem. |
|[API](#aPI)|Application Programming Interface. I Kubernetes definieras alla resurser i API, som är RESTful och exponeras via API-servern. |
|[API group](#api_group)|En uppsättning relaterade API-resurser. Till exempel finns nätverksresurser vanligtvis i networking.k8s.io-gruppen. |
|[API resource](#api_resource)|Alla Kubernetes-objekt, såsom Pods, Deployments och Services, definieras som resurser i API. |
|[API Server](#api_server)|Exponerar API via en säker port över HTTPS. Körs i kontrollplanet (control plane).|
|[Cloud controller manager](#cloud_controller_manager)| Kontrollplanskomponent som integrerar med den underliggande molnplattformen. Till exempel implementerar den logiken för att provisionera en LoadBalancer vid skapandet av en LoadBalancer Service.|
|[Cloud native](#Cloud_native)|Ett begrepp som betyder olika saker för olika människor. Generellt handlar det om hur man designar och bygger moderna applikationer och infrastruktur, som kan själv-läka, skala vid behov, utföra rolling updates och eventuellt rollbacks.|
|[ConfigMap](#ConfigMap)| Kubernetes-objekt som används för att hålla icke-känslig konfigurationsdata. Ett bra sätt att lägga till anpassad konfiguration till en generell container under körning, utan att ändra bilden.| 
|[Container](#Container)| Lättviktig miljö för att köra moderna applikationer. Varje container är ett virtuellt operativsystem med sitt eget processträd, filsystem, delade minne med mera. En container kör en applikationsprocess.| 
|[Container Network Interface (CNI)](#Container_Network_Interface_(CNI))| Pluggbar gränssnitt som möjliggör olika nätverkstopologier och arkitekturer. Tredjeparter tillhandahåller CNI-plugins som möjliggör overlay-nätverk, BGP-nätverk och olika implementationer av dessa.|
|[Container runtime](#Container_runtime)| Lågnivåprogramvara som körs på varje nod i klustret och ansvarar för att hämta containerbilder, starta och stoppa containrar, samt andra lågnivåoperationer. Typiska exempel: containerd, Docker, eller cri-o. Docker avvecklades i Kubernetes 1.20 och stödet kommer att tas bort i en framtida version.|
|[Container Runtime Interface (CRI)](#Container_Runtime_Interface_(CRI))| En lågnivåfunktion i Kubernetes som gör det möjligt att använda olika container-runtimes. Med CRI kan du välja den container-runtime som bäst passar dina behov (Docker, containerd, cri-o, kata, etc.).|
|[Container Storage Interface (CSI)](#Container_Storage_Interface_(CSI))| Gränssnitt som gör det möjligt för externa tredjeparts-lagringssystem att integreras med Kubernetes. Lagringsleverantörer skriver en CSI-drivrutin/plugin som körs som ett set Pods på ett kluster och exponerar lagringssystemets avancerade funktioner till klustret och applikationerna.|
|[Controller](#Controller)| En kontrollplansprocess som körs som en återkopplingsloop och övervakar klustret för att säkerställa att det observerade tillståndet matchar det önskade tillståndet.|
|[control plane](#control_plane)| "Hjärnan" i varje Kubernetes-kluster. Består av API, API-servern, scheduler, alla controllers med mera. Dessa komponenter körs på alla kontrollnoder (control plane nodes) i klustret.|
|[Control plane node](#Control_plane_node)| En nod i klustret som kör kontrollplanstjänster. Den kör vanligtvis inte användarapplikationer. För hög tillgänglighet bör du ha 3 eller 5 sådana noder.|
|[Cluster](#Cluster)| En uppsättning arbetarnoder och kontrollnoder som arbetar tillsammans för att köra användarapplikationer.|
|[Cluster store](#Cluster_store)| En funktion i kontrollplanet som lagrar tillståndet för klustret och applikationerna. Baserad på den distribuerade datalagringslösningen etcd och körs på kontrollplanet. Kan distribueras till ett eget kluster för bättre prestanda och högre tillgänglighet.|
|[containerd](#containerd)| Container-runtime. Standard i många moderna kluster. Donerades till CNCF av Docker, Inc.|
|[cri-o](#cri-o)| Container-runtime. Vanligt i OpenShift-baserade Kubernetes-kluster.|
|[CRUD](#CRUD)| De fyra grundläggande operationerna: Create, Read, Update och Delete som används av många lagringssystem.|
|[Custom Resource Definition (CRD)](#Custom_Resource_Definition_(CRD))| API-resurs som används för att lägga till egna resurser till Kubernetes API.|
|[Data plane](#Data_plane)| Arbetarnoderna i ett kluster som kör användarapplikationer.|
|[Deployment](#Deployment)| En controller som distribuerar och hanterar en uppsättning stateless Pods. Utför rollouts och rollbacks, och kan själv-läka. Använder en ReplicaSet-controller för att utföra skalning och själv-läkning.|
|[Desired state](#Desired_state)| Det tillstånd klustret och applikationerna ska ha. Till exempel kan det önskade tillståndet för en applikations-microservice vara 5 repliker av en viss container som lyssnar på port 8080/tcp. Detta är avgörande för återkopplingsloopar (reconciliation loops).|
|[Endpoints object](#Endpoints_object)| En uppdaterad lista över friska Pods som matchar en Service's label selector. I grund och botten är det listan över Pods som en Service kommer att skicka trafik till. Denna kommer eventuellt ersättas av EndpointSlices.|
|[etcd](#etcd)| Den öppna distribuerade databasen som används som klusterstore i de flesta Kubernetes-kluster.|
|[Ingress](#Ingress)| API-resurs som exponerar flera interna Services över en enda extern LoadBalancer Service. Arbetar på lager 7 och implementerar path-baserad och host-baserad HTTP-routing.|
|[Ingress class](#Ingress_class)| API-resurs som låter dig specificera flera olika Ingress controllers i ditt kluster.|
|[Init container](#Init_container)| En specialiserad container som körs och avslutas innan huvudapplikationscontainern startar. Används ofta för att kontrollera/initiera miljön för huvudcontainern.|
|[JSON](#JSON)| JavaScript Object Notation. Det föredragna formatet för att skicka och lagra data som används av Kubernetes.|
|[K8s](#K8s)| Förkortning för Kubernetes. "8" ersätter de åtta bokstäverna mellan "K" och "s". Uttalas "Kates".|
|[Kubectl](#Kubectl)| Kubernetes kommandoradsverktyg. Skickar kommandon till API-servern och hämtar tillståndet via API-servern.|
|[Kubelet](#Kubelet)| Den huvudsakliga Kubernetes-agenten som körs på varje nod i klustret. Den övervakar API-servern för nya arbetsuppgifter och upprätthåller en rapporteringskanal tillbaka.|
|[Kube-proxy](#Kube-proxy)| Körs på varje nod i klustret och implementerar lågnivåregler för att hantera trafikdirigering från Services till Pods. Du skickar trafik till stabila Service-namn och kube-proxy ser till att trafiken når rätt Pods.|
|[Label](#Label)| Metadata applicerad på objekt för gruppering. Fungerar tillsammans med label selectors för att matcha Pods med högre nivåers controllers. Till exempel skickar Services trafik till Pods baserat på matchande labels.|
|[Label selector](#Label_selector)| Används för att identifiera Pods som åtgärder ska utföras på. Till exempel, när en Deployment utför en rolling update vet den vilka Pods som ska uppdateras baserat på sin label selector – endast Pods med matchande labels kommer att ersättas och uppdateras.|
|[Manifest file](#Manifest_file)| En YAML-fil som innehåller konfigurationen för ett eller flera Kubernetes-objekt. Till exempel är en Service manifest file vanligtvis en YAML-fil som innehåller konfigurationen för ett Service-objekt. När du skickar en manifestfil till API-servern distribueras dess konfiguration till klustret.|
|[Microservices](#Microservices)| Ett designmönster för moderna applikationer. Applikationsfunktioner bryts upp i mindre applikationer (microservices/containers) som kommunicerar via API. De samarbetar för att bilda en användbar applikation.|
|[Namespace](#Namespace)| Ett sätt att partitionera ett enda Kubernetes-kluster i flera virtuella kluster. Bra för att tillämpa olika kvoter och åtkomstkontrollpolicyer på ett enda kluster. Inte lämpligt för stark arbetsbelastningsisolering.|
|[Node](#Node)| Även känd som worker node. Noderna i ett kluster som kör användarapplikationer. Kör kubelet, en container-runtime, och kube-proxy.|
|[Observed state](#Observed_state)| Även känt som aktuellt eller faktiskt tillstånd. Det mest uppdaterade tillståndet av klustret och de körande applikationerna. Controllers arbetar ständigt för att säkerställa att det observerade tillståndet matchar det önskade tillståndet.|
|[Orchestrator](#Orchestrator)| En programvara som distribuerar och hanterar applikationer. Moderna applikationer består av många små microservices som arbetar tillsammans för att bilda en användbar applikation. Kubernetes är orkestratorn som hanterar dessa, håller dem friska, skalar dem upp och ner med mera. Kubernetes är de facto standarden för orkestrering av microservices-applikationer baserade på containers.|
|[Persistent Volume (PV)](#persistent_volume_(pv))| Kubernetes-objekt som används för att mappa lagringsvolymer i ett kluster. Externa lagringsresurser måste mappas till PVs innan de kan användas av applikationer.|
|[Persistent Volume Claim (PVC)](#Persistent_Volume_Claim_(PVC))| Som en biljett eller kupong som tillåter en applikation att använda en Persistent Volume (PV). Utan en giltig PVC kan en applikation inte använda en PV. Kombineras ofta med StorageClasses för dynamisk volymskapning.|
|[Pod](#pod)| Den minsta enheten av schemaläggning i Kubernetes. Varje container som körs i Kubernetes måste köras inom en Pod. Podden tillhandahåller en delad exekveringsmiljö – IP-adress, volymer, delat minne etc.|
|[RBAC](#rbac)| Role-based access control. En auktoriseringsmodul som avgör om autentiserade användare kan utföra åtgärder mot klusterresurser.|
|[Reconciliation loop](#reconciliation_loop)| En controller-process som övervakar klustrets tillstånd via API-servern och säkerställer att det observerade tillståndet matchar det önskade tillståndet. De flesta controllers, såsom Deployment controller, körs som en återkopplingsloop.|
|[ReplicaSet](#replicaset)| Körs som en controller och utför själv-läkning och skalning. Används av Deployments.|
|[REST](#rest)| REpresentational State Transfer. Den vanligaste arkitekturen för att skapa webbaserade API. Använder vanliga HTTP-metoder (GET, POST, PUT, PATCH, DELETE) för att manipulera och lagra objekt.|
|[Secret](#secret)| Liknar en ConfigMap, men används för känslig konfigurationsdata. Ett sätt att lagra känslig information utanför en containerbild och infoga den i en container vid körning.|
|[Service](#service)| Med stort "S". Kubernetes-objekt för att tillhandahålla nätverksåtkomst till applikationer som körs i Pods. Genom att placera en Service framför en uppsättning Pods kan dessa Pods misslyckas, skalas upp och ner, och bytas ut utan att nätverkspunkten för åtkomst ändras. Kan integreras med molnplattformar och provisionera internet-exponerade load-balancers.|
|[Service mesh](#service_mesh)| Infrastrukturmjukvara som möjliggör funktioner såsom kryptering av Pod-till-Pod-trafik, förbättrad nätverkstelemetri och avancerad routing. Vanliga service meshes som används med Kubernetes inkluderar Consul, Istio, Linkerd, och Open Service Mesh.|
|[Sidecar](#sidecar)| En speciell container som körs bredvid och kompletterar en huvudapplikationscontainer. Service meshes implementeras ofta som sidecar-containers som injiceras i Pods och lägger till nätverksfunktioner.|
|[StatefulSet](#statefulset)| En controller som distribuerar och hanterar stateful Pods. Liknar en Deployment, men för stateful applikationer.|
|[Storage Class (SC)](#storage_class_(sc))| Ett sätt att skapa olika lagringsklasser/tier i ett kluster. Du kan till exempel ha en SC kallad "fast" som skapar NVMe-baserad lagring, och en annan SC som skapar långsammare lagring replikerad över tre platser.|
|[Volume](#volume)| En generell term för persistent lagring.|
|[Worker node](#worker_node)| En nod i klustret som kör användarapplikationer. Kallas ibland för "Node" eller "worker".|
|[YAML](#yaml)| Yet Another Markup Language. Det konfigurationsspråk du normalt skriver Kubernetes konfigurationsfiler i. Det är en utökning av JSON.|










