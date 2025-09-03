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

<details>>    

<summary> Web sunucusu nedir? API nedir? API türleri </summary>





</details>





