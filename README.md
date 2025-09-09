# trex_research
***

## 1. Modern Yazılım Geliştirme Pratikleri

  <details>
  <summary>Git nedir? GitHub nedir</summary>
    
* Git, yazılım geliştirme sürecinde kullanılan bir versiyon kontrol sistemidir.

* Kod üzerinde yapılan tüm değişiklikleri kayıt altına alır.

* Birden fazla geliştiricinin aynı proje üzerinde çakışmadan çalışabilmesine olanak sağlar.

* Geriye dönük olarak yapılan değişiklikler incelenebilir.

* GitHub ise Git’in üzerine kurulmuş bulut tabanlı bir platformdur.

* Git reposunu internette saklamaya yarar.

* Açık kaynak projelerin paylaşımı için en çok kullanılan sistemdir.

*  Ekip çalışmasını kolaylaştırmak için issue tracking (sorun takibi), pull request (katkı önerisi), GitHub Actions (otomasyon) gibi ek özellikler sunar.
 
* GitHub ise Git’in üzerine kurulmuş bulut tabanlı bir platformdur.

* Git reposunu internette saklamaya yarar.

* Açık kaynak projelerin paylaşımı<in en çok kullanılan sistemdir.

* Ekip çalışmasını kolaylaştırmak için issue tracking (sorun takibi), pull request (katkı önerisi), GitHub Actions (otomasyon) gibi ek özellikler sunar.
  
</details>

  <details>
<summary>Temel Git komutları: init, clone, add, commit, push, pull, branch, merge</summary>

*  git init

 Yeni bir Git deposu oluşturmak için kullanılır. Bir proje klasöründe git init komutu çalıştırıldığında, o klasör artık Git tarafından izlenmeye başlar. Bu sayede proje içerisinde yapılan her değişiklik Git tarafından kayıt altına    alınabilir.

 Örnek kullanım:
 
 git init


 Bu komut çalıştırıldığında klasörde .git isimli gizli bir dosya oluşur ve bu dosya projenin tüm sürüm kontrol bilgilerini içerir.

*  git clone

 Var olan bir uzak Git deposunu bilgisayara kopyalamak için kullanılır. Özellikle GitHub üzerindeki projelerin yerel ortama indirilmesinde tercih edilir.

 Örnek kullanım:

 git clone https://github.com/kullanici/proje.git


 Bu komut sayesinde uzak depodaki tüm geçmiş commitler, branchler ve dosyalar yerel bilgisayara aktarılır.

*  git add

 Dosyaları staging area (hazırlık alanı) denilen bölgeye ekler. Bu alan, commit işleminden önce değişikliklerin hazırlanmasını sağlar.

 Örnek kullanım:

 git add dosya.txt
 git add .


 İlk komut sadece belirli bir dosyayı, ikincisi ise proje içindeki tüm değişiklikleri staging alanına ekler.

*  git commit
  
 Staging alanındaki dosyaları kalıcı olarak kaydeder. Commit işlemi, yapılan değişikliklere bir “anlık görüntü” almak gibidir. Her commit, açıklayıcı bir mesajla etiketlenmelidir.

 Örnek kullanım:

 git commit -m "Login ekranı eklendi"


 Bu komut, yapılan değişikliklerin tarihçede anlamlı şekilde tutulmasına yardımcı olur.

*  git push

 Yerelde yapılan commit’lerin uzak depoya (örneğin GitHub’a) gönderilmesini sağlar. Böylece proje ekibinin diğer üyeleri de güncellenmiş koda erişebilir.

 Örnek kullanım:

 git push origin main


 Bu komut, değişiklikleri origin isimli uzak depodaki main branch’ine gönderir.

*  git pull

 Uzak depodaki en güncel değişiklikleri indirip mevcut branch ile birleştirmeye yarar. Bu komut, ekip çalışmasında başkalarının yaptığı güncellemeleri almak için sıkça kullanılır.

 Örnek kullanım:

 git pull origin main


 Böylece uzak depodaki main branch’indeki tüm yeni değişiklikler yerel bilgisayara aktarılır.

*  git branch

 Proje üzerinde dallar (branch) oluşturmaya, görüntülemeye veya yönetmeye yarar. Branch’ler, geliştiricilerin aynı proje üzerinde farklı özellikler geliştirmesini sağlar.

 Örnek kullanım:

 git branch          # mevcut branch’leri listeler
 git branch yeni-ozellik   # yeni bir branch oluşturur
 git checkout yeni-ozellik # o branch’e geçiş yapar


 Branch kullanımı, aynı projede bağımsız geliştirmelerin çakışmadan yapılabilmesine imkân verir.

*  git merge

 İki farklı branch’i birleştirmek için kullanılır. Örneğin, yeni-ozellik branch’inde geliştirilen bir özellik tamamlandığında, bu branch main ile birleştirilir.

 Örnek kullanım:

 git checkout main
 git merge yeni-ozellik


 Bu komutlar sayesinde yeni-ozellik branch’indeki değişiklikler main branch’ine eklenmiş olur. Eğer aynı    çakışan değişiklikler varsa merge conflict oluşabilir ve manuel çözüm gerekir.

</details>

<details>

 <summary>Merge conflict nedir, nasıl çözülür?</summary>
  
Merge conflict Git’te iki dal aynı dosyanın aynı bölümünü farklı şekilde değiştirdiğinde Git’in hangisini seçeceğini bilememesiyle oluşan çakışmadır. Çözümü de basittir: Çakışmalı dosyayı açıp <<<<<<<, =======, >>>>>>> işaretleri arasındaki alternatiflerden mantıklı olan içeriği oluşturacak şekilde metni düzenlersin (gerekirse birleştirebilirsn) bu işaretleri temizlersin sonra değişikliği git add ile sahneleyip git commit ile birleştirmeyi tamamlarsın.
  
 </details>

<details> 
  
<summary>CI/CD nedir? Azure DevOps, GitHub Actions ile pipeline örnekleri </summary>


* CI/CD Nedir?

CI/CD, yazılım geliştirme süreçlerinde kaliteyi artıran ve teslimat hızını yükselten bir yöntemdir.

CI (Continuous Integration – Sürekli Entegrasyon): Geliştiricilerin kodlarını sık sık ana koda entegre etmesi, bu sırada otomatik testlerin ve derleme işlemlerinin çalışmasıdır. Amaç, hataların erkenden tespit edilmesi ve kodun sürekli olarak çalışır durumda kalmasıdır.

CD (Continuous Delivery/Deployment – Sürekli Teslimat / Dağıtım): CI sonrası başarılı olan kodun otomatik olarak test ortamına veya doğrudan canlı ortama aktarılmasıdır.

Continuous Delivery: Kod otomatik olarak test/stage ortamına alınır, canlıya geçiş manuel onayla yapılır.

Continuous Deployment: Kod tüm testlerden geçtikten sonra canlıya otomatik olarak alınır.

Bu yaklaşım sayesinde:

Daha hızlı geri bildirim alınır.

Ürün kalitesi artar.

Dağıtım süreçleri standartlaşır ve insan hatası azalır.

* Azure DevOps ile Pipeline Örneği

Azure DevOps Pipelines, YAML tabanlı veya görsel olarak oluşturulabilen güçlü bir CI/CD aracıdır. Microsoft’un bulut tabanlı çözümlerine doğrudan entegredir.

Basit Azure DevOps Pipeline (YAML)

Aşağıdaki örnek bir .NET uygulaması için CI pipeline’ıdır:

trigger:
- main   # main branch'e push geldiğinde pipeline çalışır

pool:
  vmImage: 'windows-latest'

steps:
- task: UseDotNet@2
  inputs:
    packageType: 'sdk'
    version: '7.0.x'

- script: dotnet restore
  displayName: 'Restore dependencies'

- script: dotnet build --configuration Release
  displayName: 'Build project'

- script: dotnet test --no-build --verbosity normal
  displayName: 'Run tests'


Bu pipeline şu işlemleri yapar:

Main branch’e kod push edildiğinde tetiklenir.

Gerekli .NET SDK kurulumu yapılır.

Paketler restore edilir.

Proje release modda derlenir.

Unit testler çalıştırılır.

Dağıtım (CD) için ek adımlar eklenebilir. Örneğin Azure Web App’e deploy etmek için AzureWebApp task’i kullanılabilir.

* GitHub Actions ile Pipeline Örneği

GitHub Actions, GitHub üzerinde barındırılan projeler için CI/CD iş akışları kurmaya yarayan bir sistemdir. YAML dosyaları .github/workflows/ klasöründe bulunur.

Basit GitHub Actions Workflow

Aşağıdaki örnek yine bir .NET uygulaması için CI pipeline’dır:

name: .NET CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Setup .NET
      uses: actions/setup-dotnet@v3
      with:
        dotnet-version: '7.0.x'

    - name: Restore dependencies
      run: dotnet restore

    - name: Build
      run: dotnet build --configuration Release --no-restore

    - name: Test
      run: dotnet test --no-build --verbosity normal


Bu workflow şunları yapar:

Main branch’e push veya pull request geldiğinde çalışır.

Ubuntu sanal makinesi üzerinde işlem yapılır.

Kod checkout edilir.

.NET SDK yüklenir.

Restore, build ve test adımları gerçekleştirilir.

</details>

 <details>     
 
 <summary>Ek Maddeler</summary>

SDLC Aşamaları (Yazılım Geliştirme Yaşam Döngüsü)

* Planlama 

* Analiz 

* Geliştirme 

* Test 

* Dağıtım 

* Bakım
  
Metodolojiler

Agile → Esnek, hızlı geri bildirim.

Scrum → Sprint (2-4 hafta), roller (PO, SM, Dev Team).

Kanban → İş akışı panosu (To Do → Doing → Done).


 </details>
 
## 2. .NET Ekosistemi

<details>

<summary>.NET nedir? Tarihçesi amacı,neden kullanılır?</summary>

.NET Core, Windows, Linux ve MacOS için yazılım uygulamaları oluşturmak için kullanılabilecek genel amaçlı bir framework’dür. Diğer yazılımların aksine .NET Core, web uygulamaları, mobil uygulamalar, masaüstü uygulamaları, bulut hizmetleri, microservisler, API’ler, oyunlar ve IoT uygulamaları dahil olmak üzere her türlü uygulama/yazılımı oluşturmak için kullanılabilir. Diğer framework’lerden farklı olarak .NET Core, tek bir programlama diliyle sınırlı değildir ve C#, VB.NET, F#, XAML ve TypeScript’i destekler. Bu programlama dilleri açık kaynak kodludur ve bağımsız topluluklar tarafından yönetilir.

.NET Core en gelişmiş, olgun ve kapsamlı class library’leri, ortak API’leri, çoklu dil desteğini ve araçları sunmaktadır. Visual Studio ve Visual Studio Core, .NET Core’u geliştiriciler için en üretken platformlardan biri yapan en gelişmiş ve modern geliştirici IDE’leridir

2002: .NET Framework 1.0 çıktı, C# tanıtıldı (sadece Windows).

2005–2015: Framework 2.0–4.5 arasında LINQ, Async/Await gibi büyük yenilikler geldi.

2016: .NET Core yayınlandı → Açık kaynak, hızlı, platform bağımsz.

2020: .NET 5 ile Framework ve Core birleşti, tek çatı oldu.

2023+: .NET 8  Modern, çoklu platform, yapay zekâ ve bulut odaklı.

</details>

<details>
<summary>.NET Framework, .NET Core ve .NET 7/8+ farkları</summary>
  
|Özellik| .NET Framework   | .NET Core | .NET 7/8+  |
|:-----------------:|:-----------------:|:-----------------:|:-----------------:|
|Platform desteği|Yalnızca Windows'ta çalışır|Platformlar arası çalışır(Linux,Windows,Mac)|Platformlar arası çalışır|
|Güncellemeler|Güncelleme almaz|Güncelleme almaz|Güncelleme almaya devam eder|
|Kaynak kodu|Açık kaynak kodlu değil|Açık kaynak kodlu|Açık kaynak kodu|
|Desteklediği araçlar|Visual Studio|Visual Studio, VS Code, CLI araçları|Visual Studio, VS Code, CLI araçları|
|Kullanım alanları|Eski Windows uygulamaları|Çoklu platform uygulamaları, Web, API, Mikroservis|Modern çoklu platform uygulamaları, Bulut, Web API ve dahası|
|Performans|düşük|Orta|iyi performans|

</details>

<details>

<summary>Senkron ve Asenkron Programlama</summary>

* Senkron Programlama Nedir?

İşlemler ardışık olarak çalışır.

Bir işlem tamamlanmadan diğerine başlanmaz.

Program akışı, her adımda bir önceki adımın sonucunu beklemek zorundadır.

Eğer uzun süren bir işlem varsa (örneğin büyük bir dosyanın okunması, bir web servisinden veri çekilmesi), bu süre boyunca programın geri kalan kısmı çalışmaz, bekler.

* Asenkron Programlama Nedir?

İşlemler paralel veya bağımsız şekilde yürütülebilir.

Bir işlem başlatılır, o işlem arka planda devam ederken program diğer işlere geçebilir.

Program akışı, uzun süren işlemin bitmesini beklemek zorunda kalmaz.

Sonuç hazır olduğunda, program o işin sonucunu alıp kaldığı yerden devam eder.

* Senkron/Asenkron örnek senaryo açıklaması
  
HTTP çağrıları, Web API çağrıları gibi işlemler bekleme gerektirebilir. Geleneksel senkron programlama ile bu işlemleri gerçekleştirmek, aslında lokal bilgisayarın kontrolü dışında olan bir bekleme oluşturur. Bu da hem kullanıcı deneyimi hem de zaman verimliliği açısından oldukça mantıksızdır.

Kullanıcı, arka planda veri çağrıları yapılırken başka işlerle ilgilenebilmek ister. Hiçbirimiz evde bulaşık makinesi çalışıyor diye mutfakta donup kalmayız; makine işini bitirene kadar başka işlerle uğraşırız.

Senkron programlama ile bekleme gerektiren işlemleri çağırmak, bulaşık makinesinin işini bitirmesini oturup beklemek kadar verimsizdir. Asenkron programlama sayesinde ise kullanıcı, çağırdığı bir verinin gelmesini beklerken programın başka bir yerinde farklı bir işlem yapabilir ve ciddi bir zaman kazancı elde eder.

</details>

<details>
  
<summary>dotnet --info çıktısı örneği ve yorumlama</summary>

### Example output of `dotnet --info`

```
.NET SDK:
 Version:           9.0.201
 Commit:            071aaccdc2
 Workload version:  9.0.200-manifests.a3a1a094
 MSBuild version:   17.13.13+1c2026462

Runtime Environment:
 OS Name:     Windows
 OS Version:  10.0.26100
 OS Platform: Windows
 RID:         win-x64
 Base Path:   C:\Program Files\dotnet\sdk\9.0.201\

Workloads installed:
 No installed workloads found.
 Configured to use loose manifests for newly installed manifests.

Host:
  Version:      9.0.3
  Architecture: x64
  Commit:       831d23e561

.NET SDKs installed:
  9.0.201 [C:\Program Files\dotnet\sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 8.0.14 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.AspNetCore.App 9.0.3  [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 8.0.14    [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.NETCore.App 9.0.3     [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.WindowsDesktop.App 8.0.14 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
  Microsoft.WindowsDesktop.App 9.0.3  [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]

Other architectures found:
  x86   [C:\Program Files (x86)\dotnet]
    registered at [HKLM\SOFTWARE\dotnet\Setup\InstalledVersions\x86\InstallLocation]

Environment variables:
  Not set

global.json file:
  Not found
```
dotnet --info komutu, bilgisayarında kurulu olan .NET ortamını özetler. Çıktıdaki bölümler şu anlama gelir:

1. .NET SDK

Hangi SDK sürümünün kullanıldığını gösterir.

SDK (Software Development Kit), .NET projelerini derlemek ve geliştirmek için gerekli araçları içerir.

2. Runtime Environment (Çalışma Zamanı Ortamı)

İşletim sistemini (OS Name, OS Version) ve mimariyi (x64, x86, arm64 vb.) gösterir.

RID (Runtime Identifier) değeri, uygulamanın hangi platformda çalıştığını belirtir.

3. Host

.NET uygulamalarının çalıştırıldığı host ortamının sürümünü gösterir.

Burada .NET runtime versiyonu ve sistem mimarisi listelenir.

4. .NET SDKs installed

Sisteminde yüklü tüm SDK sürümlerini listeler.

Birden fazla SDK kuruluysa, projeler global.json dosyasına veya varsayılan kurallara göre uygun olanı kullanır.

5. .NET runtimes installed

Kurulu olan çalışma zamanlarını listeler.

Microsoft.NETCore.App: Konsol uygulamaları için.

Microsoft.AspNetCore.App: Web uygulamaları için.

Microsoft.WindowsDesktop.App: WinForms ve WPF uygulamaları için.

Farklı sürümlerin aynı anda kurulu olması, eski projeleri de çalıştırabilmeni sağlar.

6. Other architectures found

Ek olarak farklı mimarilerde (örneğin x86) .NET kurulmuşsa burada görünür.

7. Environment variables

.NET ile ilgili özel ortam değişkenleri tanımlandıysa burada listelenir.

8. global.json file

Projede belirli bir SDK sürümü kullanılmak istenirse global.json dosyası ile belirtilir. Eğer bulunmazsa, sistemdeki en güncel SDK kullanılır
</details>

<details>
  
<summary>arrow function (=>) ifadesinin C#’taki yeri</summary>

* Tek satırda fonksiyon tanımlama: static int Multiply(int x, int y) => x * y;
* Lambda ifadesi: Func<int, int> square = n => n * n;

  
</details>

## 3. Backend Geliştirme Temelleri

<details>  

<summary> Backend nedir? Frontend ile farkları </summary>

Front-End, kullanıcı deneyimini ve etkileşimi şekillendirirken, Back-End, web sitesinin işlevselliğini ve veri yönetimini sağlar. her iki katman da başarılı bir web sitesi için kritik öneme sahiptir ve birlikte çalışarak kullanıcıların ihtiyaçlarını karşılayan ve beklentilerini aşan bir deneyim sunarlar.
</details>

<details>    

<summary> Web sunucusu nedir? API nedir? API türleri </summary>

Web sunucusu, istemcilerden (genellikle tarayıcı) gelen HTTP/HTTPS isteklerini kabul eden ve yanıtlayan yazılım veya donanımdır.

Statik içerik (HTML, CSS, JS, resim) ya da dinamik içerik (PHP, ASP.NET, Node.js uygulamaları) dönebilir.

Tarayıcı bir siteye istek gönderdiğinde web sunucusu uygun yanıtı üretip istemciye iletir.

Örnek web sunucuları:

Apache

Nginx

IIS (Internet Information Services)

LiteSpeed

API (Application Programming Interface) Nedir?

API, bir yazılımın başka yazılımlarla haberleşmesini sağlayan arayüzdür.

İç işleyişi bilmeden, belirli kurallar (endpoint, method, veri formatı) üzerinden erişim sağlar.

En yaygın kullanılan türü Web API’lerdir.

Örnek:

Hava durumu uygulaması telefonuna veri getirmek için hava durumu API’sini kullanır.

Google Maps API, başka uygulamalara harita ekleme olanağı sağlar.

API Türleri
1. Erişim Türüne Göre

Open API (Public API): Herkesin erişimine açık.

Partner API: Sadece iş ortaklarına özel.

Private API: Sadece kurum içi kullanım için.

2. Mimarisine Göre

REST API

HTTP metodlarını (GET, POST, PUT, DELETE) kullanır.

Genellikle JSON döner.

SOAP API

XML tabanlıdır, daha katıdır.

Bankacılık gibi güvenlik kritik alanlarda kullanılır.

GraphQL API

Tek endpoint üzerinden esnek veri sorgusu yapılabilir.

gRPC

Google tarafından geliştirilmiştir.

Hızlı, binary tabanlı, mikroservisler arası iletişim için uygundur.

3. Kullanım Alanına Göre

Web API → İnternet üzerinden erişilen API’ler.

Library API → Programlama kütüphaneleri için sağlanan API’ler (.NET, Java API).

Operating System API → İşletim sistemleri ile haberleşmeyi sağlayan API’ler (Windows API, Linux system call).

</details>

<details>

<summary>HTTP nedir? HTTP metodları: GET, POST, PUT, DELETE</summary>

GET, POST, PUT, PATCH ve DELETE en sık kullanılanlardır ve HTTP protokolü üzerinden istemciler ile sunucular arasındaki iletişimin temelini oluştururlar. Bu yöntemler, World Wide Web üzerinden istemci-sunucu iletişimi sırasında bir URL ile tanımlanan bir kaynak üzerinde gerçekleştirilebilecek eylemleri tanımlar

HTTP Metodları ve Örnekler
1. GET
* Sunucudan veri istemek için kullanılır.

* Gövde (body) göndermez.
```
GET /products HTTP/1.1
Host: example.com
```
Sunucudan ürünler listesini ister.


2. POST

* Sunucuya yeni veri eklemek/göndermek için kullanılır.

* Veri body kısmında gönderilir.
```
POST /products HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Laptop",
  "price": 20000
}
```
Sunucuya yeni ürün ekler.


3. PUT

* Sunucuda var olan bir veriyi tamamen güncellemek için kullanılır.

* Gönderilen body, önceki verinin yerine geçer.
```
PUT /products/10 HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Gaming Laptop",
  "price": 25000
}
```
ID’si 10 olan ürünün tüm verisini günceller.


4. PATCH

* Sunucudaki veriyi kısmi olarak güncellemek için kullanılır.

* Sadece değişen alanlar body’de gönderilir.
```
PATCH /products/10 HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "price": 22000
}
```
Sadece fiyat bilgisini günceller.

5. DELETE

* Sunucudaki veriyi silmek için kullanılır.
```
DELETE /products/10 HTTP/1.1
Host: example.com
```
ID’si 10 olan ürünü siler.


6. HEAD

* GET gibidir ama sadece başlık (header) bilgilerini döner, gövdeyi döndürmez.
```
HEAD /products HTTP/1.1
Host: example.com
```
7. OPTIONS

* Sunucunun hangi HTTP metodlarını desteklediğini öğrenmek için kullanılır.
```
OPTIONS /products HTTP/1.1
Host: example.com
```

Cevap:
Allow: GET, POST, PUT, DELETE, OPTIONS


Özet:

GET → Veri al

POST → Yeni veri oluştur

PUT → Tam güncelle

PATCH → Kısmi güncelle

DELETE → Sil

HEAD → Sadece header bilgilerini al

OPTIONS → Desteklenen metodları öğren
  
</details>

<details>

<summary>RESTful servislerin çalışma mantığı</summary>

* REST Nedir?

Representational State Transfer (REST), web servisleri için kullanılan bir mimari tarzdır.

Amacı, HTTP protokolünün sunduğu kuralları kullanarak basit, anlaşılır ve standart bir şekilde istemci–sunucu arasında iletişim kurmaktır.

REST’i “kurallar bütünü” olarak düşünebilirsin.

* Temel Mantık

RESTful servislerde:

Her kaynak (örneğin: kullanıcı, ürün, sipariş) bir URL (endpoint) ile temsil edilir.

Bu kaynaklar üzerinde işlem yapmak için HTTP metodları (GET, POST, PUT, DELETE, PATCH…) kullanılır.

Veri genelde JSON formatında taşınır.

* Kaynak ve URI Mantığı

Her şey bir kaynaktır.

Örnek: Kullanıcı listesi → /users

Tek bir kullanıcı → /users/5

Kullanıcının siparişleri → /users/5/orders

URI, kaynağı temsil eder. Kaynağın ne olduğunu URI belirler, üzerinde ne yapılacağını HTTP metodu belirler.

* HTTP Metodları ile İşlemler

REST’te CRUD işlemleri HTTP metodlarına denk gelir:

GET /users → Tüm kullanıcıları getir

GET /users/5 → ID’si 5 olan kullanıcıyı getir

POST /users → Yeni kullanıcı oluştur

PUT /users/5 → ID’si 5 olan kullanıcıyı tamamen güncelle

PATCH /users/5 → ID’si 5 olan kullanıcıyı kısmi güncelle

DELETE /users/5 → ID’si 5 olan kullanıcıyı sil

* İstemci - Sunucu İlişkisi

İstemci (client) → Tarayıcı, mobil uygulama, masaüstü program olabilir.

Sunucu (server) → İstekleri alır, işler ve yanıt verir.

İstemci, sunucuya hangi veriyle ne yapılacağını HTTP isteği (request) ile söyler.

Sunucu, sonucu HTTP cevabı (response) olarak döner.

* Statelesness (Durumsuzluk)

RESTful servisler stateless olmalıdır.

Sunucu, her isteği bağımsız görür.

Önceki isteklerin bilgisini tutmaz.

Gerekli bilgiler (kimlik doğrulama, filtreler, parametreler) her istekte tekrar gönderilir.

* Response ve Status Codes

Sunucu her isteğe bir HTTP durum kodu döner:

200 OK → İşlem başarılı

201 Created → Yeni kaynak oluşturuldu

400 Bad Request → Hatalı istek

401 Unauthorized → Yetkisiz erişim

404 Not Found → Kaynak bulunamadı

500 Internal Server Error → Sunucu hatası

* JSON Örneği

Bir kullanıcı oluşturma isteği:
```
POST /users HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Ali",
  "email": "ali@example.com"
}
```

Sunucu cevabı:
```
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 5,
  "name": "Ali",
  "email": "ali@example.com"
}
```
</details>

<details> 

<summary>JSON veri formatı ve kullanım amacı</summary>
JSON Veri Formatı

JSON (JavaScript Object Notation), verilerin metin tabanlı olarak saklanmasını ve sistemler arasında kolayca taşınmasını sağlayan bir veri değişim formatıdır.

Özellikleri

Anahtar-değer çiftlerinden oluşur.

Diziler ve nesneler kullanılarak hiyerarşik yapı kurulabilir.

Programlama dillerinden bağımsızdır.

Hem insanlar hem makineler tarafından kolay okunabilir.

Kullanım Amacı

Web istemcisi ile sunucu arasında veri alışverişi yapmak.

Uygulamalarda yapılandırma (config) dosyası olarak kullanmak.

Farklı platform ve diller arasında veri taşımak.

Küçük, anlaşılır veri depolama ihtiyaçlarını karşılamak.

Örnek JSON Verisi
```
{
  "ad": "Ali",
  "yas": 30,
  "ogrenciMi": true,
  "dersler": ["Matematik", "Tarih", "Fizik"],
  "adres": {
    "sehir": "Bursa",
    "postaKodu": 16000
  }
}
```
Örneğin Açıklaması

* "ad": "Ali" → Anahtar ad, değeri "Ali" olan bir metin bilgisidir.

* "yas": 30 → Anahtar yas, değeri 30 olan sayısal bir bilgidir.

* "ogrenciMi": true → Anahtar ogrenciMi, değeri true olan mantıksal (boolean) bilgidir.

* "dersler": ["Matematik", "Tarih", "Fizik"] → dersler anahtarı, içinde üç eleman bulunan bir diziyi ifade eder.

* "adres": { "sehir": "Bursa", "postaKodu": 16000 } → adres anahtarı, içinde başka anahtar-değer çiftleri olan bir nesneyi temsil eder.

</details>

<details>
<summary>SOAP ve GraphQL nedir, REST’ten farkları</summary>

* SOAP (Simple Object Access Protocol)

XML tabanlı bir iletişim protokolüdür.

Katı standartlara bağlıdır (WS-Security, WS-ReliableMessaging gibi).

Yalnızca XML kullanır.

HTTP dışında SMTP, TCP gibi farklı protokollerle çalışabilir.

Daha çok bankacılık, finans, telekom gibi güvenliğin ve standartlaşmanın çok kritik olduğu alanlarda tercih edilir.

* GraphQL

Facebook tarafından geliştirilmiş, API’ler için bir sorgulama dilidir.

Tek endpoint üzerinden çalışır.

İstemci yalnızca ihtiyacı olan veriyi talep eder.

JSON formatında yanıt döner.

Over-fetching (gereğinden fazla veri çekme) ve under-fetching (eksik veri çekme) sorunlarını çözer.

Gerçek zamanlı veri için Subscriptions özelliği vardır.

* REST (Representational State Transfer)

HTTP tabanlı, en yaygın kullanılan web servis mimarisidir.

Kaynaklara HTTP metodları (GET, POST, PUT, DELETE) ile erişilir.

JSON ya da XML dönebilir (günümüzde çoğunlukla JSON).

Her kaynak için ayrı endpoint vardır (örneğin /users, /orders).

Basit, anlaşılır ve yaygın kullanımda olan bir yaklaşım sunar.

| Özellik             | SOAP                            | REST                           | GraphQL                           |
|---------------------|---------------------------------|--------------------------------|-----------------------------------|
| Veri formatı        | XML                             | JSON (çoğunlukla) / XML        | JSON                              |
| Endpoint yapısı     | Tek endpoint, karmaşık yapı     | Her kaynak için ayrı endpoint   | Tek endpoint                      |
| Esneklik            | Katı standartlı                 | Orta düzey                     | Çok esnek (yalnızca istenen veri) |
| Performans          | Ağır, yavaş                     | Hafif, genellikle hızlı         | Daha verimli                      |
| Protokol desteği    | HTTP, SMTP, TCP vb.             | HTTP                           | HTTP                              |
| Kullanım alanı      | Bankacılık, kurumsal entegrasyon| Genel web servisleri            | Modern web ve mobil API’ler       |
| Öne çıkan özellik   | Güvenlik ve standartlar         | Basitlik ve yaygınlık           | Esneklik ve özelleştirme          |  

</details>

## 4. ASP.NET

<details> 

<summary>ASP.NET ve ASP.NET Core nedir? Avantajları, farkları</summary>

ASP.NET ve ASP.NET Core, Microsoft tarafından geliştirilen web uygulama geliştirme framework’leridir. İkisi birbirine yakın kavramlar olsa da, teknoloji olarak farklı dönemleri temsil ederler.

* ASP.NET Nedir?

2002’de .NET Framework’ün bir parçası olarak tanıtıldı.

Yalnızca Windows işletim sistemi üzerinde çalışır.

Web Forms, MVC (Model-View-Controller) ve Web API gibi yaklaşımları destekler.

.NET Framework’e bağımlıdır, yani günümüzde .NET Framework 4.8’e kadar gelmiştir ve daha fazla büyük güncelleme almayacaktır.

Modern uygulamalarda “eski teknoloji” kabul ediliyor ama hâlen kurumsal projelerde yaygın olarak kullanılmakta.

* ASP.NET Core Nedir?

2016’da tanıtıldı, ASP.NET’in yeniden yazılmış, açık kaynak ve çapraz platform halidir.

Windows, Linux ve macOS üzerinde çalışır.

.NET Core üzerine kurulmuştu, şimdi .NET 5+ (günümüzde .NET 9) çatısı altında gelişiyor.

Daha hızlı, hafif ve bulut tabanlı uygulamalara uygun.

Web API ve MVC birleşmiş durumda → tek bir yapıdan hem web sayfası hem API geliştirilebilir.

Dependency Injection, Middleware, Minimal API gibi modern mimari özellikleri destekler.

* ASP.NET Avantajları

Uzun yıllardır kullanılan, olgun bir framework.

Kurumsal projelerde hâlâ çok geniş kullanım alanı var.

Windows Server + IIS entegrasyonu güçlü.

Büyük topluluk ve çok sayıda hazır kütüphane mevcut.

* ASP.NET Core Avantajları

Çapraz platform (Windows, Linux, macOS).

Performansı yüksek, özellikle Kestrel web server sayesinde.

Açık kaynak ve sürekli gelişiyor.

Bulut dostu, container (Docker, Kubernetes) ile kolayca dağıtılabilir.

Daha esnek: Middleware tabanlı mimari → geliştirici kendi pipeline’ını kurabilir.

Minimal API ve gRPC desteği sayesinde mikroservislerde ideal.

| Özellik          | ASP.NET                      | ASP.NET Core                               |
|------------------|------------------------------|--------------------------------------------|
| **Çıkış Yılı**   | 2002                         | 2016                                       |
| **Çalışma Ortamı** | Sadece Windows              | Windows, Linux, macOS                     |
| **Performans**   | Daha düşük, IIS bağımlı      | Yüksek, Kestrel + IIS/NGINX                |
| **Framework**    | .NET Framework               | .NET 5/6/7/8/9                             |
| **Mimari**       | Web Forms, MVC, Web API ayrı | MVC + API birleşik, Middleware tabanlı     |
| **Açık Kaynak**  | Hayır                        | Evet                                       |
| **Gelecek**      | Yeni geliştirme yok          | Aktif olarak geliştiriliyor                |

</details>

<details> 

<summary>MVC nedir, ne için kullanılınır</summary>

MVC (Model-View-Controller), yazılım geliştirmede kullanılan bir mimari desendir.

* Model (M): Uygulamanın verilerini ve iş kurallarını temsil eder. (Örn: Veritabanı işlemleri, iş mantığı)

* View (V): Kullanıcıya gösterilen arayüzdür. (Örn: HTML sayfası, UI ekranı)

* Controller (C): Kullanıcıdan gelen isteği alır, işleyip uygun Model ve View’i yönlendirir.

Ne için kullanılır?
Uygulamalarda katmanlı yapı sağlar. Kodun okunabilirliğini, bakımını ve test edilebilirliğini kolaylaştırır. Web uygulamalarında en çok tercih edilen desenlerden biridir.

</details>

<details>
  
<summary>Middleware nedir, nasıl çalışır</summary>

* Middleware, farklı uygulamalar, sistemler ve veritabanları arasında etkileşim ve veri akışı sağlayan bulut hizmetleridir. Uygulamalar ve veriler arasında bir köprü görevi görür bu sayede sistemler arasında kesintisiz iletişim sağlar ve veri akışını düzenler.
ASP.NET Core uygulamalarında middleware, gelen HTTP isteğinin geçtiği aşamaları belirleyen işlem hattıdır. Her middleware isteği işleyebilir, sonraki aşamaya gönderebilir veya sonlandırabilir. Bu yüzden eklenme sırası çok önemlidir. Yanlış sıralama, kimlik doğrulama ve yetkilendirme gibi kritik işlevlerin devre dışı kalmasına yol açar.

Doğru Sıralama Örneği
```
app.UseRouting();          
app.UseAuthentication();   
app.UseAuthorization();    
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllers();
});
```
Özetle

* UseRouting() → Rotaları hazırlar.

* UseAuthentication() → Kullanıcıyı doğrular.

* UseAuthorization() → Yetki kontrolü yapar.

* UseEndpoints() → İsteği ilgili endpoint’e yönlendirir.
  
</details>

<details>

<summary>Dependency Injection (DI) nedir, neden önemlidir</summary>

  
</details>




