# SİPARİŞ YÖNETİM SİSTEMİ 

" Görüntülediğiniz SQL senaryosu, 
BTK Akademi adresinde bulunan "Uygulamalarla SQL Öğreniyorum" eğitiminden 
pratik yapma amacıyla alınmıştır. 
Eğitimde kullanılan veri tabanını, eğitimin dökümantasyon kısmından görüntüleyebilirsiniz. " 


# Senaryo 1 : Sipariş veren kişiler arasından FATURASI GÖNDERİLMİŞ olan kişilerin bilgisini çekeceğiz.
( Yani siparişi ulaşmış kişilerin bilgisi de diyebiliriz. )

Projede çeşitli tabloları birleştirerek, siparişler hakkında kapsamlı bilgi sunan bir sorgu geliştirilmiştir.

Aşağıdaki bilgileri sunan bir sorgu oluşturulmuştur:

- Kullanıcı Adı (USERS tablosundan)
- Ad Soyad (USERS tablosundan)
- İl (CITIES tablosundan)
- İlçe (TOWNS tablosundan)
- Semt (DISTRICTS tablosundan)
- Açık Adres (ADDRESS tablosundan)
- Sipariş ID (ORDERS tablosundan)
- Sipariş Tarihi (ORDERS tablosundan)
- Toplam Tutar (ORDERS tablosundan)
- Ödeme Tarihi (PAYMENTS tablosundan)
- Banka Onay Kodu (PAYMENTS tablosundan)
- Fatura Tarihi (INVOICES tablosundan)
- Kargo Fiş No (INVOICES tablosundan) ALINACAKTIR. (Kod kısmında da bu detayları görüntüleyebilirsiniz)

Burada tabloların hepsi birbiri ile bağlantılıdır. Bu sebeple tablolar arasında INNER JOIN kullanılarak veriler birleştirilmiştir :

- USERS ve ORDERS: Kullanıcı bilgileri, sipariş bilgileri ile birleştirilir (U.ID = O.USERID).
- ADDRESS ve CITIES, TOWNS, DISTRICTS: Açık adres bilgileri şehir, ilçe ve semt bilgileriyle birleştirilir (A.ID = O.ADDRESSID, A.CITYID = CT.ID, A.TOWNID = T.ID, A.DISTRICTID = D.ID).
- ORDERS ve PAYMENTS: Siparişler, ödeme bilgileriyle birleştirilir (P.ORDERID = O.ID).
- ORDERS ve INVOICES: Siparişler, fatura bilgileriyle birleştirilir (I.ORDERID = O.ID).
- WHERE koşulu, belirli bir kullanıcının bilgilerini çekmek için kullanılır. 
'Belirli Bir Kullanıcı Adı' kısmını sorgulamak istediğiniz kullanıcının adıyla değiştirerek istediğiniz kişiye ait sipariş sorgusunu gerçekleştirebilirsiniz. 


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# ORDER MANAGEMENT SYSTEM

" The SQL scenario you are viewing was taken from the "I'm Learning SQL with Applications" training on BTK Academy for practice purposes.

You can view the database used in the training from the documentation section of the training. "

# Scenario 1: We will retrieve the information of the people who have an INVOICE SENT among the people who placed an order.
# (In other words, we can also say the information of the people whose orders have reached.)

A query has been developed in the project that combines various tables and provides comprehensive information about orders.

A query is created that provides the following information:

- User Name (from USERS table)
- Name Surname (from USERS table)
- Province (from CITIES table)
- District (from TOWNS table)
- District (from DISTRICTS table)
- Full Address (from ADDRESS table)
- Order ID (from ORDERS table)
- Order Date (from ORDERS table)
- Total Amount (from ORDERS table)
- Payment Date (from PAYMENTS table)
- Bank Approval Code (from PAYMENTS table)
- Invoice Date (from INVOICES table)
- Cargo Receipt No (from INVOICES table) WILL BE TAKEN.

Here, all the tables are related to each other. For this reason, the data is combined using INNER JOIN between the tables:

- USERS and ORDERS: User information is combined with order information (U.ID = O.USERID).
- ADDRESS and CITIES, TOWNS, DISTRICTS: Full address information is combined with city, district and neighborhood information (A.ID = O.ADDRESSID, A.CITYID = CT.ID, A.TOWNID = T.ID, A.DISTRICTID = D.ID).
- ORDERS and PAYMENTS: Orders are combined with payment information (P.ORDERID = O.ID).
- ORDERS and INVOICES: Orders are combined with invoice information (I.ORDERID = O.ID).
- The WHERE condition is used to retrieve information for a specific user.
You can perform an order query for any person by replacing the 'Specific User Name' section with the name of the user you want to query.
