# 🌿 Green Axis (Yeşil Eksen)

**Agricultural and Industrial Waste Management System**

Green Axis is an administrative platform that monitors and manages the agricultural and industrial waste management process. This system manages waste trading between farms, companies, and chambers, and measures sustainability impact.

---

## 📋 Table of Contents

- [Features](#-features)
- [System Requirements](#-system-requirements)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Database](#-database)
- [User Roles](#-user-roles)
- [Technologies](#-technologies)
- [Development](#-development)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### 🏢 Company Management
- Company registration and approval processes
- Company information management
- Company document upload and viewing
- Company listing and detail viewing

### 🌾 Farm Management
- Farm registration and approval processes
- Farm information management
- Farm product management
- Farm document upload and viewing

### 📦 Product Management
- Agricultural waste product registration
- Product category management
- Product quantity tracking
- Product document management

### 📝 Purchase Requests
- Companies requesting products from farms
- Request approval/rejection processes
- Request status tracking
- Request history viewing

### 📊 Reporting
- **General Reports**: System-wide statistics
- **SDG Reports**: Sustainable Development Goals reports
  - Recovered waste quantity (tons)
  - Prevented CO₂ emissions (tons)
  - Economic value added (TL)
- **Excel Export**: Export reports in Excel format

### 🔐 User Management
- Role-based access control
- Secure login system
- User session management
- Operation logs

### 📄 Document Management
- PDF document upload
- Document viewing
- Document categories
- QR code generation

---

## 💻 System Requirements

### Minimum Requirements
- **Operating System**: Windows 7 or higher
- **.NET Framework**: 4.7.2 or higher
- **RAM**: 2 GB
- **Disk Space**: 500 MB
- **Screen Resolution**: 1024x768

### Recommended Requirements
- **Operating System**: Windows 10/11
- **RAM**: 4 GB or higher
- **Disk Space**: 1 GB
- **Screen Resolution**: 1920x1080

---

## 🚀 Installation

### 1. Download the Project
```bash
git clone https://github.com/username/VirtualProgramming-Final_Project.git
cd VirtualProgramming-Final_Project
```

### 2. Open with Visual Studio
1. Open the `YesilEksen.sln` file with Visual Studio
2. Visual Studio will automatically restore NuGet packages
3. If packages are not restored, right-click on the project in Solution Explorer and select "Restore NuGet Packages"

### 3. Database Setup
- The `YesilEksen.db` database file is automatically created when the application is first run
- The database is created in the application's execution folder (`bin\Debug` or `bin\Release`)

### 4. Build and Run
1. Press `F5` in Visual Studio or click the "Start Debugging" button
2. The application will compile and run

### 5. Test Users
The following test users are automatically created when the application is first run:

| Username | Password | Role |
|----------|----------|------|
| `sanayi_admin` | `123456` | Industry Chamber Admin |
| `ziraat_admin` | `123456` | Agriculture Chamber Admin |

---

## 📖 Usage

### Logging In
1. Launch the application
2. Enter your username and password
3. Click the "Login" button
4. You will be redirected to the relevant dashboard based on your role

### Industry Chamber Admin Panel
- **Company Approval**: View and approve/reject companies that have applied
- **Purchase Requests**: Manage purchase requests made by companies from farms
- **Reporting**: Generate general reports and SDG reports
- **Companies**: List all companies and view their details

### Agriculture Chamber Admin Panel
- **Farm Approval**: View and approve/reject farms that have applied
- **Product Approval**: Approve/reject products added by farms
- **Reporting**: Generate general reports and SDG reports
- **Farms**: List all farms and view their details

### Company User
- View and update your company information
- Request products from farms
- Track your request statuses
- Upload your documents

### Farm User
- View and update your farm information
- Add and manage your products
- View incoming requests
- Upload your documents

---

## 📁 Project Structure

```
VirtualProgramming-Final_Project/
│
├── YesilEksen/
│   ├── Sanayi/              # Industry Chamber modules
│   │   ├── SanayiFirmaOnay.cs
│   │   ├── SanayiAlımTalebi.cs
│   │   └── SanayiGenelRapor.cs
│   │
│   ├── Tarım/               # Agriculture Chamber modules
│   │   ├── ÇiftlikOnay.cs
│   │   ├── ÇitflikÜrünOnay.cs
│   │   ├── Çİftçi-Dasboard.cs
│   │   ├── GenelRapor.cs
│   │   └── SdkRapor.cs
│   │
│   ├── Belgeler/            # PDF documents folder
│   │
│   ├── Resources/           # Images and resources
│   │
│   ├── DatabaseHelper.cs    # Database operations
│   ├── ExcelHelper.cs       # Excel operations
│   ├── Session.cs           # Session management
│   ├── Login.cs             # Login form
│   ├── Form1.cs             # Main dashboard (Industry)
│   ├── Firmalar.cs          # Company list
│   ├── Ciftlikler.cs        # Farm list
│   ├── Urunler.cs           # Product list
│   └── ...
│
├── packages/                # NuGet packages
│
└── YesilEksen.sln           # Visual Studio solution file
```

---

## 🗄️ Database

### Database Structure

The application uses SQLite database. The database file (`YesilEksen.db`) is automatically created in the application's execution folder.

### Main Tables

- **Tbl_Firmalar**: Company information
- **Tbl_Ciftlikler**: Farm information
- **Tbl_Kullanicilar**: User information
- **Tbl_CiftlikUrunleri**: Farm products
- **Tbl_AlimTalepleri**: Purchase requests
- **Tbl_CiftlikBelgeleri**: Farm documents
- **Tbl_FirmaBelgeleri**: Company documents
- **Tbl_UrunBelgeleri**: Product documents
- **Tbl_IslemLoglari**: Operation logs
- **Tbl_SdgRaporVerisi**: SDG report data

### Lookup Tables

- **Tbl_Sehirler**: City list
- **Tbl_Sektorler**: Sector list
- **Tbl_UrunKategorileri**: Product categories
- **Tbl_OnayDurumlari**: Approval statuses (Pending, Approved, Rejected)
- **Tbl_Roller**: User roles

### Database Operations

Database operations are performed through the `DatabaseHelper` class:

```csharp
// Execute query
DataTable dt = DatabaseHelper.ExecuteQuery("SELECT * FROM Tbl_Firmalar");

// Insert/update/delete data
int result = DatabaseHelper.ExecuteNonQuery("INSERT INTO ...");

// Get single value
object count = DatabaseHelper.ExecuteScalar("SELECT COUNT(*) FROM ...");
```

---

## 👥 User Roles

### 1. Company (RoleID: 1)
- View and update company information
- Request products from farms
- Track request statuses
- Upload documents

### 2. Farm (RoleID: 2)
- View and update farm information
- Add and manage products
- View incoming requests
- Upload documents

### 3. Industry Chamber Admin (RoleID: 3)
- Approve/reject company registrations
- Manage purchase requests
- Generate general reports
- Generate SDG reports
- View system statistics

### 4. Agriculture Chamber Admin (RoleID: 4)
- Approve/reject farm registrations
- Approve/reject product registrations
- Generate general reports
- Generate SDG reports
- View system statistics

---

## 🛠️ Technologies

### Framework and Platform
- **.NET Framework 4.7.2**
- **Windows Forms**
- **C# 7.3**

### Database
- **SQLite 1.0.119.0**
- **System.Data.SQLite**

### NuGet Packages
- **EPPlus 8.3.1**: Excel file operations
- **QRCoder 1.7.0**: QR code generation
- **System.Buffers 4.5.1**: Buffer management
- **System.Memory 4.5.5**: Memory management
- **System.ComponentModel.Annotations 5.0.0**: Data annotations
- **System.Security.Cryptography.Xml 8.0.2**: XML encryption

### Development Environment
- **Visual Studio 2017 or higher**
- **.NET Framework 4.7.2 SDK**

---

## 🔧 Development

### Setting Up the Development Environment

1. **Clone the repository**
   ```bash
   git clone https://github.com/username/VirtualProgramming-Final_Project.git
   ```

2. **Open in Visual Studio**
   - Open the `YesilEksen.sln` file

3. **Restore NuGet packages**
   - Right-click on the project in Solution Explorer
   - Select "Restore NuGet Packages"

4. **Build the project**
   - Press `Ctrl+Shift+B` or Build > Build Solution

### Database Test Data

To add test data, you can use the `InsertSyntheticData()` method found in the `DatabaseHelper` class. This method adds:
- 50+ cities
- 50+ sectors
- 50+ product categories
- 50+ companies
- 50+ farms
- 50+ users
- 50+ products
- 50+ purchase requests
- 50+ documents
- 50+ operation logs
- 50+ SDG report data entries

### Code Standards

- **Naming**: PascalCase (classes, methods), camelCase (variables)
- **XML Documentation**: All public methods must include XML documentation
- **Error Handling**: Try-catch blocks should be used and meaningful messages should be shown to users
- **Database**: All database operations must be performed through the `DatabaseHelper` class

---

## 🤝 Contributing

To contribute:

1. Fork this repository
2. Create a new branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

### Contribution Guidelines

- Follow code standards
- Write tests for new features
- Update the README
- Use meaningful commit messages

---

## 📝 Changelog

### Version 1.0.0
- Initial release
- Basic company and farm management
- Approval processes
- Reporting modules
- Document management
- Excel export

---

## 🐛 Known Issues

- Database performance may decrease as the file grows (will be optimized in future versions)
- Multi-user support is limited (SQLite WAL mode is used)

---

## 🔮 Future Features

- [ ] Web API integration
- [ ] Mobile application support
- [ ] Advanced reporting and charts
- [ ] Email notifications
- [ ] Multi-language support
- [ ] Cloud database support
- [ ] Automatic backup system

---

## 📞 Contact

<<<<<<< HEAD
For questions or suggestions:
- **GitHub Issues**: [Issues page](https://github.com/keremmisik/VirtualProgramming-Final_Project/issues)
- **Email**: [email address](keremisik1010@gmail.com)
=======
Sorularınız veya önerileriniz için:
- **GitHub Issues**: [Issues sayfası](https://github.com/keremmisik/VirtualProgramming-Final_Project/issues)
- **E-posta**: [e-posta adresi](keremisik1010@gmail.com)
>>>>>>> 71d934210defbecc40edebd16998da159871e773

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- EPPlus team for Excel operations
- QRCoder team for QR code support
- SQLite team for database support
- All contributors

---

## 📚 Additional Resources

- [.NET Framework Documentation](https://docs.microsoft.com/en-us/dotnet/framework/)
- [SQLite Documentation](https://www.sqlite.org/docs.html)
- [EPPlus Documentation](https://github.com/EPPlusSoftware/EPPlus)
- [QRCoder Documentation](https://github.com/codebude/QRCoder)

---

**Green Axis** - For a sustainable future 🌱
