## Türkçe Auto-GPT: Otonom Bir GPT-4 Deneyimi 


Auto-GPT, GPT-4 dil modelinin yeteneklerini sergileyen deneysel bir açık kaynaklı uygulamadır. GPT-4 tarafından yönetilen bu program, belirlediğiniz hedefe özel bir şekilde ulaşmak için çalışıyor. Tamamen otonom olarak çalışan GPT-4'ün ilk örneklerinden biri olan Auto-GPT, yapay zeka ile mümkün olanın sınırlarını zorluyor.

## 🚀 Features

- 🌐 Arama ve bilgi toplama için internet erişimi
- 💾 Uzun Süreli ve Kısa Süreli hafıza yönetimi
- 🧠 Metin üretimi için GPT-4 örnekleri
- 🔗 Popüler web sitelerine ve platformlara erişim
- 🗃️ GPT-3.5 ile dosya depolama ve özetleme

## 📋 Gereksinimler

- Python 3.8 veya üstü (adımlar: [Windows için](https://www.tutorialspoint.com/how-to-install-python-in-windows) /
                                 [Mac için](https://www.dataquest.io/blog/installing-python-on-mac/))
- [OpenAI API key](https://platform.openai.com/account/api-keys)

### Opsiyonel
- ElevenLabs Key (Yapay Zeka'nın konuşmasını istiyorsanız)

## ⚠️ OpenAI API Keys konfigürasyon ⚠️ 

OpenAI API anahtarınızı şu adresten alın:: https://platform.openai.com/account/api-keys.

#### **LÜTFEN DEVAM ETMEDEN ÖNCE BU ADIMI YAPTIĞINIZDAN EMİN OLUN, YOKSA HİÇBİR ŞEY ÇALIŞMAZ!**

## 💾 Kurulum

Auto-GPT'yi yüklemek için şu adımları izleyin:

1. Yukarıda listelenen tüm **gereksinimlere** sahip olduğunuzdan emin olun, yoksa yükleyin/alın

_Aşağıdaki komutları çalıştırmak için, bilgisayarınızdaki bir klasöre gidip üstteki klasör yoluna 'CMD' yazarak bir CMD, Bash veya Powershell penceresi açın, ardından enter tuşuna basın._

2. Depoyu klonlayın: Bu adım için Git'in kurulu olması gerekir.Proje dizinine gidin: (Bunu CMD pencerenize yazın, CMD penceresinde az önce indirdiğiniz depoya gitmeyi hedefliyorsunuz)

    ```bash
    git clone https://github.com/YusufBehramBayindir/Auto-GPT.git
    ```

3. Deponun indirildiği dizine gidin

    ```bash
    cd Auto-GPT
    ```

4. Gerekli bağımlılıkları kurun

    ```bash
    pip install -r requirements.txt
    ```

5. Auto-GPT'yi yapılandırın
    1. Ana "/Auto-GPT" klasöründe ".env.template" adlı dosyayı bulun.
    2. ".template" uzantısını kaldırarak bu dosyanın ".env" adlı bir kopyasını oluşturun. En kolay yol, bunu bir komut istemi/terminal penceresinde `cp .env.template .env` yapmaktır.
    3. `.env` dosyasını bir metin düzenleyicide açın. _Not: Nokta ile başlayan dosyalar İşletim Sisteminiz tarafından gizlenmiş olabilir._
    4. "OPENAI_API_KEY=" yazan satırı bulun.
    5. `"="` işaretinden sonra benzersiz OpenAI API Anahtarınızı girin (tırnak işaretleri veya boşluklar olmadan).
    6. Kullanmak istediğiniz hizmetler için diğer API anahtarlarını veya Simgelerini girin.
    7. ".env" dosyasını kaydedip kapatın.

    Bu adımları tamamlayarak, projeniz için API Anahtarlarını doğru şekilde yapılandırdınız.
   
   - OpenAI API anahtarınızı almak için [OpenAI API Anahtarları Yapılandırması](#openai-api-keys-configuration) konusuna bakın.
   - ElevenLabs API anahtarınızı şu adresten edinin: https://elevenlabs.io. Web sitesindeki "Profil" sekmesini kullanarak xi-api-key'inizi görüntüleyebilirsiniz.
   - GPT'yi bir Azure örneğinde kullanmak istiyorsanız, `USE_AZURE` öğresini `True` olarak ayarlayın ve ardından şu adımları izleyin:
     -  `azure.yaml.template` öğresini `azure.yaml`  olarak yeniden adlandırı ve `azure_api_base`, `azure_api_version` ve ilgili modeller için tüm dağıtım kimliklerini `azure_model_map` bölümünde sağlayın:
       - `fast_llm_model_deployment_id` - gpt-3.5-turbo veya gpt-4 deployment ID
       - `smart_llm_model_deployment_id` - gpt-4 deployment ID
       - `embedding_model_deployment_id` - text-embedding-ada-002 v2  deployment ID
     - Lütfen bu değerlerin tümünü çift tırnaklı dizeler olarak belirtin
        ```yaml
        # Köşeli parantezler (<>) içindeki dizeyi kendi kimliğiniz ile değiştirin
        azure_model_map:
          fast_llm_model_deployment_id: "<my-fast-llm-deployment-id>"
         ...
       ```

     - Ayrıntılar burada bulunabilir: https://pypi.org/project/openai/ in the `Microsoft Azure Endpoints` section and here: https://learn.microsoft.com/en-us/azure/cognitive-services/openai/tutorials/embeddings?tabs=command-line for the embedding model.

## 🔧 kullanım

1. Terminalinizde `autogpt` Python modülünü çalıştırın

    ```
    python -m autogpt
    ```

2. Her eylemden sonra, komut(lar)ı yetkilendirmek için seçenekler arasından seçim yapın,
programdan çıkın veya yapay zekaya geri bildirim sağlayın.
    1. Tek bir komutu yetkilendirin, "y" girin
    2. Bir dizi _N_ sürekli komut yetkilendirin, `y -N` girin
    3. Programdan çıkın, `n` girin


### Logs

Etkinlik ve hata günlükleri "./output/logs" klasöründe bulunur.

Hata ayıklama günlüklerini yazdırmak için:

```
python -m autogpt --debug
```

### Komut Satırı Argümanları
Auto-GPT'yi çalıştırırken kullanabileceğiniz bazı yaygın argümanlar şunlardır:
> Açılı parantez (<>) içindeki her şeyi belirtmek istediğiniz bir değerle değiştirin

* Mevcut tüm komut satırı argümanlarını görüntüleyin
     ``` bash
     piton -m autogpt --help
     ```
* Auto-GPT'yi farklı bir AI Ayarları dosyasıyla çalıştırın
     ``` bash
     python -m autogpt --ai-settings <dosyaadı>
     ```
* Bir bellek arka ucu belirtin
     ``` bash
     python -m autogpt --use-memory <memory-backend>
     ```

> **NOT**: Bu örneklerden bazıları için kısa yollar vardır, örneğin "--use-memory" için "-m". Daha fazla bilgi için "python -m autogpt --help" kullanın

## 🗣️ Konuşma Modu
Auto-GPT için TTS'yi _(Text-to-Speech)_  kullanmak üzere bunu kullanın

```bash
python -m autogpt --speak
```

### On bir laboratuvardan gelen adlara sahip kimlik listesi, adı veya ID kullanabilirsiniz:

- Rachel : 21m00Tcm4TlvDq8ikWAM
- Domi : AZnzlk1XvdvUeBnXmlld
- Bella : EXAVITQu4vr4xnSDxMaL
- Antoni : ErXwobaYiN019PkySvjV
- Elli : MF3mGyEYCl7XYWbV9V6O
- Josh : TxGEqnHWrfWFTfGW9XjX
- Arnold : VR6AewLTigWG4xSOukaG
- Adam : pNInz6obpgDQGcFmaJgB
- Sam : yoZ06aMxZJJ28mfd3POQ

## 🔍 Google API Anahtarları Yapılandırması

Bu bölüm isteğe bağlıdır, bir google araması yaparken 429 hatasıyla ilgili sorun yaşıyorsanız resmi google api'yi kullanın.
"google_official_search" komutunu kullanmak için ortam değişkenlerinizde Google API anahtarlarınızı ayarlamanız gerekir.
1. [Google Bulut Konsoluna](https://console.cloud.google.com/) gidin.
2. Halihazırda bir hesabınız yoksa, bir hesap oluşturun ve oturum açın.
3. Sayfanın üst kısmındaki "Bir Proje Seçin" açılır menüsüne ve ardından "Yeni Proje"ye tıklayarak yeni bir proje oluşturun. Bir isim verin ve "Oluştur" u tıklayın.
4. [API'ler ve Hizmetler Panosuna](https://console.cloud.google.com/apis/dashboard) gidin ve "API'leri ve Hizmetleri Etkinleştir"i tıklayın. "Custom Search API"yi arayın ve üzerine tıklayın, ardından "Etkinleştir"e tıklayın.
5. [Kimlik Bilgileri](https://console.cloud.google.com/apis/credentials) sayfasına gidin ve "Kimlik Bilgileri Oluştur"u tıklayın. "API Anahtarı"nı seçin.
6. API anahtarını kopyalayın ve makinenizde "GOOGLE_API_KEY" adlı bir ortam değişkeni olarak ayarlayın. Aşağıdaki ortam değişkenlerini ayarlama konusuna bakın.
7. Projenizde Özel Arama API'sini [etkinleştirin](https://console.developers.google.com/apis/api/customsearch.googleapis.com). (Yayılması için birkaç dakika beklemeniz gerekebilir)
8. [Özel Arama Motoru](https://cse.google.com/cse/all) sayfasına gidin ve "Ekle"yi tıklayın.
9. Yönergeleri izleyerek arama motorunuzu kurun. Tüm web'de veya belirli sitelerde arama yapmayı seçebilirsiniz.
10. Arama motorunuzu oluşturduktan sonra, "Denetim Masası"na ve ardından "Temel Bilgiler"e tıklayın. "Arama motoru kimliğini" kopyalayın ve makinenizde "CUSTOM_SEARCH_ENGINE_ID" adlı bir ortam değişkeni olarak ayarlayın. Aşağıdaki ortam değişkenlerini ayarlama konusuna bakın.

_Ücretsiz günlük özel arama kotanızın yalnızca 100 adede kadar aramaya izin verdiğini unutmayın. Bu sınırı artırmak için, günlük 10.000 adede kadar aramadan kar elde etmek için projeye bir faturalandırma hesabı atamanız gerekir._

### Ortam değişkenlerini ayarlama

Windows Kullanıcıları için:

```bash
setx GOOGLE_API_KEY "YOUR_GOOGLE_API_KEY"
setx CUSTOM_SEARCH_ENGINE_ID "YOUR_CUSTOM_SEARCH_ENGINE_ID"
```

macOS ve Linux kullanıcıları için:

```bash
export GOOGLE_API_KEY="YOUR_GOOGLE_API_KEY"
export CUSTOM_SEARCH_ENGINE_ID="YOUR_CUSTOM_SEARCH_ENGINE_ID"
```

## Önbellek Türünüzü Ayarlama

Varsayılan olarak, Auto-GPT redis veya Pinecone yerine LocalCache kullanacaktır.

İkisinden birine geçmek için `MEMORY_BACKEND` ortam değişkenini istediğiniz değerle değiştirin:

* "yerel" (varsayılan), yerel bir JSON önbellek dosyası kullanır
* "pinecone", ENV ayarlarınızda yapılandırdığınız Pinecone.io hesabını kullanır
* `redis`, yapılandırdığınız redis önbelleğini kullanır
* `milvus`, yapılandırdığınız milvus önbelleğini kullanır
* "weaviate", yapılandırdığınız weaviate önbelleğini kullanır

## Memory Backend Setup

### Redsıs Kurulumu
> _**DİKKAT**__ \
Bu, herkesin erişebileceği şekilde tasarlanmamıştır ve güvenlik önlemlerinden yoksundur. Bu nedenle, Redis'i şifre olmadan veya hiç internete maruz bırakmaktan kaçının.
1. Docker'ı (veya Windows'ta Docker Desktop'ı) kurun
2. Redis kapsayıcısını başlatın
    ```bash
    docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest
    ```
    > Parola ayarlamak ve ek yapılandırma için https://hub.docker.com/r/redis/redis-stack-server adresine bakın.
3. `.env`de aşağıdaki ayarları yapın
     > Açılı parantez içindeki **ŞİFRE**'yi değiştirin (<>)
    ```bash
    MEMORY_BACKEND=redis
    REDIS_HOST=localhost
    REDIS_PORT=6379
    REDIS_PASSWORD=<PASSWORD>
    ```

    İsteğe bağlı olarak Redis'te saklanan belleğin kalıcı olması için 'WIPE_REDIS_ON_START=False' ayarını yapabilirsiniz.

Redis için bellek dizinini aşağıdakileri kullanarak belirleyebilirsiniz:
```bash
MEMORY_INDEX=<WHATEVER>
```

### 🌲 Pinecone API Key Setup

Pinecone, herhangi bir zamanda aracı için yalnızca ilgili anıların yüklenmesine izin vererek, çok miktarda vektör tabanlı belleğin depolanmasını sağlar.

1. Henüz bir hesabınız yoksa [pinecone](https://app.pinecone.io/) adresine gidin ve bir hesap oluşturun.
2. Ücret ödememek için "Başlangıç" planını seçin.
3. Sol kenar çubuğundaki varsayılan proje altında API anahtarınızı ve bölgenizi bulun.

`.env` dosya kümesinde:
- `PINECONE_API_KEY`
- `PINECONE_ENV` (example: _"us-east4-gcp"_)
- `MEMORY_BACKEND=pinecone`

Alternatif olarak, bunları komut satırından ayarlayabilirsiniz (gelişmiş):

Windows Kullanıcıları için:

```bash
setx PINECONE_API_KEY "<YOUR_PINECONE_API_KEY>"
setx PINECONE_ENV "<YOUR_PINECONE_REGION>" # e.g: "us-east4-gcp"
setx MEMORY_BACKEND "pinecone"
```

macOS ve Linux kullanıcıları için:

```bash
export PINECONE_API_KEY="<YOUR_PINECONE_API_KEY>"
export PINECONE_ENV="<YOUR_PINECONE_REGION>" # e.g: "us-east4-gcp"
export MEMORY_BACKEND="pinecone"
```

### Milvus Kurulumu

[Milvus](https://milvus.io/), çok büyük miktarda vektör tabanlı bellek depolamak ve ilgili hızlı arama sağlamak için açık kaynaklı, yüksek düzeyde ölçeklenebilir bir vektör veritabanıdır.

- milvus veritabanını kurun, uyumlu sorunları önlemek için pymilvus sürümünüzü ve milvus sürümünüzü aynı tutun.
   - açık kaynaklı kurulum [Milvus'u Yükle](https://milvus.io/docs/install_standalone-operator.md)
   - veya [Zilliz Cloud](https://zilliz.com/cloud) tarafından kurulum
- ".env" içindeki "MILVUS_ADDR"yi "host:ip" milvus adresinize ayarlayın.
- Milvus'u arka uç olarak etkinleştirmek için ".env" içindeki "MEMORY_BACKEND" öğesini "milvus" olarak ayarlayın.

**İsteğe bağlı:**
- milvus koleksiyon adını istediğiniz gibi değiştirmek için `.env` içinde `MILVUS_COLLECTION` ayarını yapın, `autogpt` varsayılan addır.


### Weaviate Kurulumu
[Weaviate](https://weaviate.io/) açık kaynaklı bir vektör veri tabanıdır. Veri nesnelerini ve ML modellerinden vektör katıştırmalarını depolamaya izin verir ve sorunsuz bir şekilde milyarlarca veri nesnesine ölçeklendirir. [Bir Weaviate örneği, yerel olarak (Docker kullanılarak), Kubernetes üzerinde veya Weaviate Bulut Hizmetleri kullanılarak oluşturulabilir](https://weaviate.io/developers/weaviate/quickstart).
Hala deneysel olmasına rağmen, Auto-GPT işleminin kendisinin bir Weaviate örneğini başlatmasına izin veren [Embedded Weaviate](https://weaviate.io/developers/weaviate/installation/embedded) desteklenmektedir. Etkinleştirmek için, "USE_WEAVIATE_EMBEDDED" öğesini "True" olarak ayarlayın ve "weaviate-client>=3.15.4" kurulumunu pip olarak yaptığınızdan emin olun.

#### Weaviate istemcisini kurun

Kullanımdan önce Weaviate istemcisini kurun.

```
$ pip yükleme weaviate-client
```

#### Ortam değişkenlerini ayarlama

`.env` dosyanızda aşağıdakileri ayarlayın:

```
MEMORY_BACKEND=weaviate
WEAVIATE_HOST="127.0.0.1" # the IP or domain of the running Weaviate instance
WEAVIATE_PORT="8080" 
WEAVIATE_PROTOCOL="http"
WEAVIATE_USERNAME="your username"
WEAVIATE_PASSWORD="your password"
WEAVIATE_API_KEY="your weaviate API key if you have one"
WEAVIATE_EMBEDDED_PATH="/home/me/.local/share/weaviate" # this is optional and indicates where the data should be persisted when running an embedded instance
USE_WEAVIATE_EMBEDDED=False # set to True to run Embedded Weaviate
MEMORY_INDEX="Autogpt" # name of the index to create for the application
```
 
## Bellek Kullanımını Görüntüle

`--debug` bayrağını kullanarak bellek kullanımını görüntüleyin :)


## 🧠 Bellek ön tohumlama
Bellek ön tohumlama, dosyaları belleğe almanıza ve Auto-GPT'yi çalıştırmadan önce ön tohumlama yapmanıza olanak tanır.

``` bash
# python data_ingestion.py -h 
usage: data_ingestion.py [-h] (--file FILE | --dir DIR) [--init] [--overlap OVERLAP] [--max_length MAX_LENGTH]

Bir dosyayı veya birden fazla dosya içeren bir dizini belleğe alın. Bu komut dosyasını çalıştırmadan önce .env'nizi ayarladığınızdan emin olun.

options:
  -h, --help               bu yardım mesajını göster ve çık
  --file FILE              Alınacak dosya.
  --dir DIR                Alınacak dosyaları içeren dizin.
  --init                   Belleği başlatın ve içeriğini silin (varsayılan: Yanlış)
  --overlap OVERLAP        Dosyaları alırken parçalar arasındaki örtüşme boyutu (varsayılan: 200)
  --max_length MAX_LENGTH  Dosyaları alırken her parçanın maksimum uzunluğu (varsayılan: 4000)

# python data_ingestion.py --dir DataFolder --init --overlap 100 --max_length 2000
```
Yukarıdaki örnekte, komut dosyası belleği başlatır, "Auto-Gpt/autogpt/auto_gpt_workspace/DataFolder" dizini içindeki tüm dosyaları, 100'lük parçalar arasında çakışma ve her bir parçanın maksimum uzunluğu 2000 olacak şekilde belleğe alır.

Tek bir dosyayı belleğe almak için "--file" bağımsız değişkenini de kullanabileceğinizi ve data_ingestion.py'nin yalnızca "/auto_gpt_workspace" dizini içindeki dosyaları alacağını unutmayın.

DIR yolu, auto_gpt_workspace dizinine göredir, yani `python data_ingestion.py --dir . --init`, `auto_gpt_workspace` dizinindeki her şeyi alır.

Bu belleği "hatırladığında" belgelerin yapay zekaya sunulma biçimine ince ayar yapmak için "maks_uzunluk" ve çakışma parametrelerini ayarlayabilirsiniz:
- Örtüşme değerinin ayarlanması, AI'nın bilgileri geri çağırırken her yığından daha fazla bağlamsal bilgiye erişmesine olanak tanır, ancak daha fazla parçanın oluşturulmasına ve dolayısıyla bellek arka uç kullanımının ve OpenAI API isteklerinin artmasına neden olur.
- "max_length" değerinin düşürülmesi, bağlamda daha fazla mesaj geçmişine izin vererek bilgi istemi belirteçlerini kaydedebilen daha fazla parça oluşturacaktır, ancak aynı zamanda parça sayısını da artıracaktır.
- "max_length" değerini artırmak, yapay zekaya her parçadan daha fazla bağlamsal bilgi sağlayarak oluşturulan parça sayısını azaltır ve OpenAI API isteklerinde tasarruf sağlar. Ancak bu, daha fazla bilgi istemi belirteci kullanabilir ve yapay zekanın kullanabileceği genel bağlamı azaltabilir.

Bellek ön tohumlama, ilgili verileri belleğine alarak AI doğruluğunu artırmaya yönelik bir tekniktir. Veri yığınları bölünür ve belleğe eklenir, bu da AI'nın bunlara hızlı bir şekilde erişmesine ve daha doğru yanıtlar üretmesine olanak tanır. Büyük veri kümeleri için veya belirli bilgilere hızlı bir şekilde erişilmesi gerektiğinde kullanışlıdır. Örnekler, Auto-GPT'yi çalıştırmadan önce API veya GitHub belgelerinin alınmasını içerir.

⚠️ Memory olarak Redis kullanıyorsanız, `.env` dosyanızda Auto-GPT'yi `WIPE_REDIS_ON_START=False` ile çalıştırdığınızdan emin olun.

⚠️Diğer bellek arka uçları için, şu anda Auto-GPT'yi başlatırken belleği zorla siliyoruz. Bu bellek arka ucuyla veri almak için, Otomatik GPT çalışması sırasında istediğiniz zaman "data_ingestion.py" komut dosyasını arayabilirsiniz.

Anılar, Auto-GPT çalışırken alınsalar bile alındıkları anda yapay zeka tarafından kullanılabilir.

## 💀 Sürekli Mod ⚠️

AI'yı **kullanıcı yetkilendirmesi olmadan** çalıştırın, %100 otomatik.
Sürekli mod önerilmez.
Potansiyel olarak tehlikelidir ve AI'nızın sonsuza kadar çalışmasına veya normalde izin vermeyeceğiniz eylemleri gerçekleştirmesine neden olabilir.
Kendi sorumluluğunuzdadır kullanın.

1. Terminalinizde `autogpt` python modülünü çalıştırın:

    ```bash
    python -m autogpt --speak --continuous
    ```

2. Programdan çıkmak için Ctrl + C tuşlarına basın

## GPT3.5 ONLY Mode

GPT4 api'ye erişiminiz yoksa, bu mod Auto-GPT'yi kullanmanıza izin verecektir!

```bash
python -m autogpt --speak --gpt3only
```

Ana bilgisayarın sistemine ve verilerine herhangi bir zarar gelmemesi için yüksek güvenlik önlemleri gerektiren görevler için sanal makine kullanılması önerilir.

## 🖼 Görüntü Oluşturma

Varsayılan olarak Auto-GPT, görüntü oluşturma için DALL-e'yi kullanır. Stable Diffusion'ı kullanmak için [Hugging Face API Simgesi](https://huggingface.co/settings/tokens) gereklidir.

Bir jetonunuz olduğunda, ".env" dosyanızda şu değişkenleri ayarlayın:

```bash
IMAGE_PROVIDER=sd
HUGGINGFACE_API_TOKEN="YOUR_HUGGINGFACE_API_TOKEN"
```

## Selenium
```bash
sudo Xvfb :10 -ac -screen 0 1024x768x24 & DISPLAY=:10 <YOUR_CLIENT>
```

## ⚠️ sınırlamalar

Bu deney, GPT-4'ün potansiyelini sergilemeyi amaçlamaktadır, ancak bazı sınırlamalarla birlikte gelir:

1. Parlatılmış bir uygulama veya ürün değil, sadece bir deney
2. Karmaşık, gerçek dünyadaki iş senaryolarında iyi performans göstermeyebilir. Aslında, gerçekten yaparsa, lütfen sonuçlarınızı paylaşın!
3. Çalıştırması oldukça pahalıdır, bu nedenle OpenAI ile API anahtar limitlerinizi belirleyin ve izleyin!

## 🛡Feragatname

Bu proje, Auto-GPT, deneysel bir uygulamadır ve açık veya zımni herhangi bir garanti olmaksızın "olduğu gibi" sağlanmaktadır. Bu yazılımı kullanarak, veri kaybı, sistem arızası veya ortaya çıkabilecek diğer sorunlar dahil ancak bunlarla sınırlı olmamak üzere, kullanımıyla ilgili tüm riskleri üstlenmeyi kabul edersiniz.

Bu projenin geliştiricileri ve katkıda bulunanları, bu yazılımın kullanılması sonucunda meydana gelebilecek herhangi bir kayıp, hasar veya diğer sonuçlar için herhangi bir sorumluluk veya yükümlülük kabul etmez. Auto-GPT tarafından sağlanan bilgilere dayanarak alınan tüm kararlardan ve eylemlerden yalnızca siz sorumlusunuz.

**Token kullanımı nedeniyle GPT-4 dil modeli kullanımının pahalı olabileceğini lütfen unutmayın.** Bu projeyi kullanarak, kendi belirteç kullanımınızı ve ilgili maliyetleri izlemekten ve yönetmekten sorumlu olduğunuzu kabul edersiniz. Beklenmeyen ücretleri önlemek için OpenAI API kullanımınızı düzenli olarak kontrol etmeniz ve gerekli limitleri veya uyarıları ayarlamanız önemle tavsiye edilir.

Otonom bir deney olarak Auto-GPT, gerçek dünyadaki iş uygulamalarına veya yasal gerekliliklere uygun olmayan içerikler üretebilir veya eylemler gerçekleştirebilir. Bu yazılımın çıktısına dayalı olarak alınan tüm eylemlerin veya kararların geçerli tüm yasalara, düzenlemelere ve etik standartlara uygun olmasını sağlamak sizin sorumluluğunuzdadır. Bu projenin geliştiricileri ve katkıda bulunanları, bu yazılımın kullanımından doğacak sonuçlardan sorumlu tutulamaz.

Auto-GPT'yi kullanarak, geliştiricileri, katkıda bulunanları ve tüm bağlı tarafları her türlü talep, zarar, kayıp, sorumluluk, maliyet ve harcamaya (makul avukatlık ücretleri dahil) karşı tazmin etmeyi, savunmayı ve masun tutmayı kabul edersiniz. Bu yazılımı kullanmanızdan veya bu şartları ihlal etmenizden kaynaklanan.

## Testleri çalıştır

Tüm testleri çalıştırmak için aşağıdaki komutu çalıştırın:

```bash
pytest 

```

To run just without integration tests:

```
pytest --without-integration
```

To run just without slow integration tests:

```
pytest --without-slow-integration
```

To run tests and see coverage, run the following command:

```bash
pytest --cov=autogpt --without-integration --without-slow-integration
```
