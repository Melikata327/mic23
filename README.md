## آزمایش شماره شش : اندازه گیری دما و رطوبت با سنسور DHT11 
### هدف 

در این آزمایش می خواهیم با استفاده از سنسور <strong>DHT11</strong>، میزان دما و رطوبت محیط را سنجیده و بر اساس آن کولر یا هیتر را روشن کنیم.

---

### مواد و وسایل مورد نیاز 

---

### توضیحات کلی 

سنسور DHT11 از یک حسگر خازنی برای اندازه گیری رطوبت استفاده می کند. این حسگر از یک صفحه فلزی و یک صفحه عایق تشکیل شده است. هنگامی که رطوبت هوا به صفحه فلزی برخورد می کند، ظرفیت صفحه افزایش می یابد. این افزایش ظرفیت توسط حسگر اندازه گیری می شود و به عنوان داده رطوبت ارائه می شود.  
DHT11 همچنین از یک حسگر مقاومتی برای اندازه گیری دما استفاده می کند. این حسگر از یک مقاومت NTC تشکیل شده است. با افزایش دما، مقاومت NTC کاهش می یابد. این کاهش مقاومت توسط حسگر اندازه گیری می شود و به عنوان داده دما ارائه می شود.

 در ابتدا کتابخانه مربوط به سنسور را وارد می کنیم. سپس پینی که به پایه شماره 2 سنسور متصل شده است ( پین 8 ) به عنوان DHTPIN معرفی می کنیم.
در تابع setup سریال مانیتور و همچنین DHT11 را آغاز می کنیم. پین شماره 7 را به عنوان خروجی برای یکی از LED ها ( نماینده کولر ) و پین شماره 6 را برای LED دیگر ( نماینده heater ) قرار می دهیم. در تابع loop هر یک ثانیه یکبار مقدار رطوبت و مقدار دما را از سنسور می خوانیم و آن ها را بر روی سریال مانیتور چاپ می کنیم. در نهایت شرطی را تعیین می کنیم که اگر دما بیشتر از 27 درجه بود LED که مربوط به کولر است روشن شود و LED مربوط به هیتر خاموش شود در غیر این صورت برعکس این عمل اتفاق بیفتد.
در ابتدا، پین تغذیه سنسور را به ولتاژ 5V و پین زمین را به زمین متصل کنید. پس از آن، پین Data را به یک پین دیجیتال شماره  6 متصل کنید.

علاوه بر این، لازم است که یک مقاومت pull-up برابر 10 کیلو اهمی را بین پین VCC و خط داده قرار دهید
---

### سورس کد 
```cpp
int heater 6;

void setup() {

Serial.begin(9600);

Serial.printing DHTil test");

dht.begin();

pinMode (cooler, OUTPUT);

pinMode (heater, OUTPUT);

void loop() {

float humid dht.readHumidity();

float tempdht.readTemperature();

Serial.print("The Temporary is: ");

Serial.print(temp);

Serial.println("*C");

Serial.print("The Humidity is: ");

Serial.print (humid);

Serial.println("*");

delay(1000);

if (temp > 27) {

digitalWrite(cooler, HIGH);

digitalWrite (heater, LOW);

else if (temp <27) {

digitalWrite (cooler, LOW);
}
```
---

### نتیجه گیری 
سنسور DHT11 می تواند در طیف وسیعی از کاربردها از جمله خانه ها، سیستم های آبیاری و گلخانه ها، بیمارستان ها و... به کار رود. بزرگترین عیب این سنسور دقت نسبتا پایین آن در اندازه گیری دما ( حدود 2 درجه سلسیوس ) می باشد.## آزمایش شماره شش : اندازه گیری دما و رطوبت با سنسور DHT11 
### هدف 

در این آزمایش می خواهیم با استفاده از سنسور <strong>DHT11</strong>، میزان دما و رطوبت محیط را سنجیده و بر اساس آن کولر یا هیتر را روشن کنیم.

---

### مواد و وسایل مورد نیاز 

---

### توضیحات کلی 

سنسور DHT11 از یک حسگر خازنی برای اندازه گیری رطوبت استفاده می کند. این حسگر از یک صفحه فلزی و یک صفحه عایق تشکیل شده است. هنگامی که رطوبت هوا به صفحه فلزی برخورد می کند، ظرفیت صفحه افزایش می یابد. این افزایش ظرفیت توسط حسگر اندازه گیری می شود و به عنوان داده رطوبت ارائه می شود.  
DHT11 همچنین از یک حسگر مقاومتی برای اندازه گیری دما استفاده می کند. این حسگر از یک مقاومت NTC تشکیل شده است. با افزایش دما، مقاومت NTC کاهش می یابد. این کاهش مقاومت توسط حسگر اندازه گیری می شود و به عنوان داده دما ارائه می شود.

 در ابتدا کتابخانه مربوط به سنسور را وارد می کنیم. سپس پینی که به پایه شماره 2 سنسور متصل شده است ( پین 8 ) به عنوان DHTPIN معرفی می کنیم.
در تابع setup سریال مانیتور و همچنین DHT11 را آغاز می کنیم. پین شماره 7 را به عنوان خروجی برای یکی از LED ها ( نماینده کولر ) و پین شماره 6 را برای LED دیگر ( نماینده heater ) قرار می دهیم. در تابع loop هر یک ثانیه یکبار مقدار رطوبت و مقدار دما را از سنسور می خوانیم و آن ها را بر روی سریال مانیتور چاپ می کنیم. در نهایت شرطی را تعیین می کنیم که اگر دما بیشتر از 27 درجه بود LED که مربوط به کولر است روشن شود و LED مربوط به هیتر خاموش شود در غیر این صورت برعکس این عمل اتفاق بیفتد.
در ابتدا، پین تغذیه سنسور را به ولتاژ 5V و پین زمین را به زمین متصل کنید. پس از آن، پین Data را به یک پین دیجیتال شماره  6 متصل کنید.

علاوه بر این، لازم است که یک مقاومت pull-up برابر 10 کیلو اهمی را بین پین VCC و خط داده قرار دهید
---

### سورس کد
```cpp
int heater 6;

void setup() {

Serial.begin(9600);

Serial.printing DHTil test");

dht.begin();

pinMode (cooler, OUTPUT);

pinMode (heater, OUTPUT);

void loop() {

float humid dht.readHumidity();

float tempdht.readTemperature();

Serial.print("The Temporary is: ");

Serial.print(temp);

Serial.println("*C");

Serial.print("The Humidity is: ");

Serial.print (humid);

Serial.println("*");

delay(1000);

if (temp > 27) {

digitalWrite(cooler, HIGH);

digitalWrite (heater, LOW);

else if (temp <27) {

digitalWrite (cooler, LOW);
}
```
---

### نتیجه گیری 
سنسور DHT11 می تواند در طیف وسیعی از کاربردها از جمله خانه ها، سیستم های آبیاری و گلخانه ها، بیمارستان ها و... به کار رود. بزرگترین عیب این سنسور دقت نسبتا پایین آن در اندازه گیری دما ( حدود 2 درجه سلسیوس ) می باشد.
