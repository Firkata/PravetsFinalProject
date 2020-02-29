# PravetsFinalProject
Template for final project of the course

<b>Connect to Database</b>
  - Create Database in Management Studio
  - In <b>appsettings.json</b> edit DefaultConnection to <b>Server=.;Database=NameOfCreatedDB;...</b>
  
<b>Create custom user</b>
  - Create class <b>ApplicationUser.cs</b> that inherits from IdentityUser and add properties (FirstName, LastName etc.)
  - Set <b>ApplicationDbContext.cs</b> to inherit from IdentityDbContext<ApplicationUser>
  - In Startup.cs put <b>ApplicationUser</b> instead of <b>IdentityUser</b> in <b>services.AddDefaultIdentity</b>
  - At the first row in <b>_LoginPartial.cshtml</b> set <b>SignInManager</b> and <b>UserManager</b> to use <b>ApplicationUser</b>
  
<b>Create custom Register</b>
  - Right click on project name and select <b>Add->New Scaffolded Item..</b>
  - Choose <b>Identity</b> and click <b>Add</b> and wait
  - Choose checkbox <b>Account\Register</b>
  - Select <b>ApplicationDBContext</b> as <b>Data context class</b> and click <b>Add</b>
  - Go to <b>Register.cshtml</b> and add new divs for every property of ApplicationUser.cs similar to <b>Input.Email</b>
  - Go to <b>Register.cs</b> and add new properties in <b>InputModel</b> similar to Email
  - In same file go to <b>OnPostAsync</b> and add the new fields to <b>ApplicationUser instance</b> (FirstName = Input.FirstName etc.)
  
  To model database open <b>Package Manager Console</b> and write:
    Add-Migration CreateCustomUser
    Update-Database
