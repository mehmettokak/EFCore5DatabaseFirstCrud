
MSSQL Veritabanı için aşağıdaki DLL indirilir.

-Microfost.EntityFrameworkCore.SqlServer
-Microsoft.EntityFramework.Tools



Run Package Manager Console dan aşağıda seçtiğiniz komut çalıştırın

1- Create DatabaseFirst
Scaffold-DbContext -provider Microsoft.EntityFrameworkCore.SqlServer -connection "Data Source= (localdb)\MSSQLLocalDB; initial catalog=dbEF; trusted_connection=yes;" -OutputDir "Models\DataBaseFirst\Entity" -ContextDir "Models\DataBaseFirst\Context"

2- Get For  DataAnnotations
Scaffold-DbContext -provider Microsoft.EntityFrameworkCore.SqlServer -connection "Data Source= (localdb)\MSSQLLocalDB; initial catalog=dbEF; trusted_connection=yes;" -OutputDir "Models\DataBaseFirst\Entity" -ContextDir "Models\DataBaseFirst\Context" -DataAnnotations

3- 
Update model (tablo kolon ekleme,tablo ekleme,tablo silme gibi guncelleme yaptıysak modeli aşağıdaki gibi guncelliyoruz.)
Scaffold-DbContext -provider Microsoft.EntityFrameworkCore.SqlServer -connection "Data Source= (localdb)\MSSQLLocalDB; initial catalog=dbEF; trusted_connection=yes;" -OutputDir "Models\DataBaseFirst\Entity" -ContextDir "Models\DataBaseFirst\Context" -DataAnnotations -f

Startup.cs de yeralan ConfigureServices metoduna  services.AddDbContext<dbEFContext>(); ekliyoruz. 


---POSTGRESQL veri Tabanı Kullanıyorsak----------
Postgresql 
-Npgsql.EntityFrameworkCore.PostgreSql ddli indiriyoruz.
 
 DatabaseFirst için aşağıdaki komut çalıştırılır.
-Scaffold-DbContext -provider Npgsql.EntityFrameworkCore.PostgreSQL -connection "Host=localhost;Database=test11;User Id=postgres;Password=123456;Port=5432" -OutputDir "Models\DataBaseFirstPostgreSql\Entity" -ContextDir "Models\DataBaseFirstPostgreSql\Context"
  
-startup.cs de ConfigureServices metoduna services.AddDbContext<test11Context>(); eklenir.
