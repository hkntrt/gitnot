#### GIT NOTLARI

S1. Proje dizininde git nasıl aktive edilir?

```sh
git init
```
---

S2. Git için kullanıcı yerel düzeyde kullanıcı adı ve email nasıl değiştirilir?

```sh
git config user.name "kullanıcı_adı"
git config user.email "kullanıcı_adı@mail.com"
```
---

S3. Git için kullanıcı global yerel düzeyde kullanıcı adı ve email nasıl değiştirilir?

```sh
git config --global user.name "kullanıcı_adı"
git config --global user.email "kullanıcı_adı@mail.com"
```

NOT: Eğer yerel düzeyde kullanıcı ismi ve epostası tanımlamazsanız proje otomatik olarak global için olanları kullanır.

---

S4. Git için genel bir çalışma döngüsü nasıldır?

(Dizinimizde bulunan dosyalar - untracked) -> Staging Area -> Commit

---

S5. Git `staging area` nedir?

Staging area değişikliklerin commit yapılmadan önce saklandığı yerdir. Burada commit yapılacak değişiklikleri görebilir istersek daha ufak commitlere ayırabiliriz veya geri alabiliriz.

---

S6. Staging area'ya nasıl dosya eklenir?

Eklemek istediğiniz dosyanın adını `git add dosya_adı` şeklinde yazarak veya hepsini eklemek için `.` kullanmak.

```sh
git add Program.cs #Program.cs adlı dosyayı staging area'ya ekler
git add . #Proje dizininde bulunan bütün dosyaları ekler, genel olarak bu seçenek kullanılır ama .gitignore dosyaysı oluşturmakta fayda var.
```
---

S7. .gitignore dosyası nedir?

Ne olursa olsun staging areaya eklenmemesi gereken dosyalar vardır. Bunların çoğunluğu üçüncü parti paketler, geçici dosyalar veya derlenmiş ikili dosyalar olabilir. Genel olarak `git add .` ie yapılan eklemelerde bütün dizin beraber eklendiği için gereksiz dosyalar da onlarla beraber staging areaya gitmesin diye bu dosya kullanılır. Visual Studio bunu otomatik olarak oluşturur eğer giti
visual studio ile kullanırsanız.

---

S8. Commit nasıl yapılır?

Önce dosyaları staging areaya eklemelisin daha sonra `commit` komutuyla bu işlemi gerçekleştirebilirsin.

```sh
git add . #herşeyi staging areaya gönder
git commit -m "commit mesajı" #-m ektra bir mentin editörü açmadan konsolda comit mesajı vermek için
git commit # eğer bu şekilde yaparsanız karşınıza bir editör penceresi açılacak hangi editör olacağını git ayarlarından değiştirebilirsiniz.
```
---

S9. Git branch nasıl eklenir?

```sh
git branch branch_adı
```
---

S10. Var olan branchler nasıl listelenir?

```sh
git branch
```

---

S11. Branchler arası geçiş nasıl yapılır?

```sh
git checkout branch_adi
```

---

S12. Branch nasıl silinir?

```sh
#aşağıdaki her iki komut aynı işi yapar
git branch --delete branch_adı
git branch -d branch_adı
```

---

S13. Uzak server nasıl eklenir?

```
git remote add origin git@github.com:user_name/repo_name.git
```
NOT: Her zaman önce pull daha sonra push yapmak gerekir ki oluşacak conflictler bütün ekibe yansımasın.

---

S14. Uzak servera nasıl kod gönderilir? (`push`)

Push komutu ile gönderilir.

```sh
git push origin master / main # kısa bir süre önce master branch adı main'e dönüştü siyahi halkları desteklemek için dikkat etmekte fayda var.
```

Yukarıdaki komuta hangi branch adını girerseniz o branche gönderilecek kodlar. Eğer kodların yerelde tutulduğu branch uzak serverda yoksa otomatik olarak oluşturulacak.

---

S15. Uzak serverdan kod nasıl çekilir? (`pull`)

```sh
git pull origin main # origin uzak server, main ise yerelde hangi brancha kaydedileceği
```

---

S16. 