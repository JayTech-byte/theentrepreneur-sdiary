JAMES MWANGI 
BSC SOFTWARE ENGINEERING 
SC212/0591/2022 
SCS202-PROGRAMMING AND DATABASE 
PRACTICUM 
 
Contents 
CHAPTER 1: INTRODUCTION ........................................................................................................... 4 
1.1 Project Overview .................................................................................................................. 4 
PROJECT SCOPE: THE ENTREPRENEUR'S DIARY –........................................................................ 4 
DIVINE DASHBOARD .................................................................................................................... 4 
Technical Scope ............................................................................................................................... 5 
Sales Management: ........................................................................................................................ 6 
Historical AnalyƟ cs: ........................................................................................................................ 6 
User Experience: ............................................................................................................................. 6 
Technical ImplementaƟ on .............................................................................................................. 6 
DESIGN ............................................................................................................................................ 9 
Key RelaƟ onships:........................................................................................................................ 9 
2. ApplicaƟ on ↔ Data Layer: ................................................................................................... 14 
3. Cross-Layer Dependencies: ................................................................................................... 14 
4. External IntegraƟ ons: ............................................................................................................ 15 
Component CharacterisƟ cs: .......................................................... Error! Bookmark not defined.
Data Flow PaƩ erns: ....................................................................... Error! Bookmark not defined.
Security Boundaries: ..................................................................... Error! Bookmark not defined.
EvoluƟ onary Paths: ........................................................................ Error! Bookmark not defined.
TESTING ..................................................................................................................................... 15 
RelaƟ onships ............................................................................................................................. 20 
Data Flow RelaƟ onships ............................................................................................................ 21 
Forms ......................................................................................................................................... 21 
Constraints................................................................................................................................. 22 
Advanced Constraints & Relationships 5.1 Cross-Entity Validation javascript ........................ 24 
Temporal RelaƟ onships ............................................................................................................. 24 
Database Table DefiniƟ ons .................................................................................................... 25 
Indexes for Common Queries ................................................................................................ 26 
ReferenƟ al Integrity PaƩ erns ................................................................................................. 26 
Temporal Table RelaƟ onships ................................................................................................ 27 
DenormalizaƟ on Strategy ...................................................................................................... 27 
Check Constraint Workarounds (SQLite LimitaƟ ons) ............................................................ 27 
TABLES ....................................................................................................................................... 28 
DOMAIN CONSTRAINTS ............................................................................................................. 33 
Project Report: Entrepreneur's Diary System ............................................................................. 39 
REFERENCES .................................................................................................................................. 42 
SCREENSHOTS ............................................................................................................................ 43 
CONCLUSION ............................................................................................................................. 45 
REFERENCES .................................................................................................................................. 46 
 
CHAPTER 1: INTRODUCTION 
1.1 Project Overview 
A comprehensive business management web app designed for entrepreneurs to track inventory, 
sales, and financial metrics with an inspiraƟ onal interface. Combines operaƟ onal funcƟ onality 
with moƟ vaƟ onal storytelling elements. 
PROJECT SCOPE: THE ENTREPRENEUR'S DIARY – 
DIVINE DASHBOARD 
Purpose 
The Entrepreneur's Diary - Divine Dashboard is a comprehensive business management tool 
designed to empower small and medium-sized enterprises (SMEs) and solo entrepreneurs in 
Kenya to streamline operaƟ ons, track financial performance, and make data-driven decisions. 
Key ObjecƟ ves 
1. OperaƟ onal Efficiency: 
o Automate inventory and sales tracking o 
Calculate real-Ɵ me profit margins and revenue o 
Maintain immutable historical records for 
audiƟ ng 
2. Financial Clarity: 
o Provide acƟ onable insights through dynamic 
reports o Highlight top-performing products and 
sales trends o Forecast inventory requirements 
and cash flow 
3. User Empowerment: 
o Simplify business management for non￾technical users o Offer intuiƟ ve visualizaƟ ons of 
key metrics o Encourage growth through 
performance analyƟ cs 
 
Core Features 
Table 1CORE CAPTION 
Feature FuncƟ onality 
Inventory 
Management 
Track stock levels, cost prices, and profit margins in real-Ɵ me (KSh) 
Sales Tracking Record transacƟ ons, monitor revenue streams, and analyze sales 
paƩ erns 
Historical Logging Maintain tamper-proof records of inventory changes and sales history 
Financial ReporƟ ng Generate P&L statements, inventory valuaƟ ons, and sales performance 
summaries 
User AuthenƟ caƟ on Secure access control with profile management and data isolaƟ on 
MoƟ vaƟ onal Interface Blend funcƟ onal dashboards with inspiraƟ onal content for user 
engagement 
Technical Scope
1. Frontend: 
Responsive web interface opƟ mized for mobile-first design. 
Dynamic visualizaƟ ons with parƟ cle-animated background for aestheƟ c appeal.
OpƟ mized for on-the-go access, ensuring usability on both desktop and mobile devices. 
2. Backend: 
Client-side data management using localStorage for user account persistence. 
Business logic focused on financial calculaƟ ons such as profit per unit and sales performance.
Robust security safeguards ensuring secure handling of user data. 
3. Data Model: 
RelaƟ onal structure to model inventory-sales relaƟ onships.
Temporal tables for storing historical data, allowing for Ɵme-based filtering and analysis. 
Denormalized reporƟ ng tables for improved performance during data retrieval.
Core Features 
User AuthenƟ caƟ on:
Secure user signup and login system with support for profile pictures. 
Password complexity requirements (minimum 8 characters, including uppercase and numbers). 
Session management with logout funcƟ onality and local storage persistence for user data.
Inventory Management: 
Real-Ɵ me inventory tracking, including cost price, selling price, and quanƟ ty.
Automated profit calculaƟ ons per unit and total inventory profit.
Historical logging with Ɵmestamps for inventory changes.
Sales Management:
Sales transacƟ on recording system with dynamic profit calculaƟ ons.
VisualizaƟ on of sales performance, including revenue, gross profit, and inventory-linked cost 
deducƟ ons.
Historical AnalyƟ cs:
Immutable logs for inventory and sales changes. 
Time-based filtering for trend analysis and financial insights. 
User Experience:
ParƟ cle animaƟ on background and responsive design opƟ mized for both desktop and mobile.
Dashboard navigaƟ on system with interacƟ ve elements such as success/error noƟ ficaƟ ons and 
input validaƟ on.
InteracƟ ve tables with sorƟ ng capabiliƟ es and progress indicators.
Technical ImplementaƟ on
Frontend Stack: 
Pure JavaScript (no frameworks), using the Canvas API for animaƟ ons.
CSS3 Custom ProperƟ es for styling, uƟ lizing modern layout techniques (Flexbox/Grid).
Google Fonts for professional typography (Montserrat, Playfair Display). 
Data Management: 
localStorage is used for persisƟ ng user accounts, inventory history, and sales records.
Data structure: 
Inventory items: {id, name, cost, price, quanƟ ty}
Sales transacƟ ons: {id, item, quanƟ ty, price}
Security: 
Client-side data validaƟ on, input saniƟ zaƟ on, and password verificaƟ on.
Basic safeguards for data persistence with localStorage. 
Business Logic: 
Financial CalculaƟ ons: 
Inventory profit: profitPerUnit = sellingPrice - costPrice 
Total profit: totalProfit = profitPerUnit * quanƟ ty
Sales analyƟ cs: revenue = salePrice * quanƟ tySold, profit = (salePrice - inventoryCost) * 
quanƟ tySold
Inventory-Sales IntegraƟ on: 
AutomaƟ c cost price retrieval from inventory.
Real-Ɵ me profit impact visualizaƟ on with implied stock level warnings.
User Experience Design 
Visual Theme: 
Dark mode interface with gold accent colors (#fdd835). 
Professional typography (Montserrat/Playfair Display). 
Card-based layout system for beƩ er content organizaƟ on.
InteracƟ ve Elements:
Animated buƩ ons with hover effects.
Blur effect overlays for aestheƟ c enhancement.
Responsive tables with sorƟ ng and progress indicators.
Error Handling: 
Form validaƟ on feedback, input boundary checks, and data type enforcement.
Local storage failure fallbacks to maintain system stability. 
LimitaƟ ons & Boundaries
Current Scope: 
Single-user system with browser-only data persistence. 
Hardcoded currency in KSh (Kenyan Shilling). 
No data export/import funcƟ onality or mulƟ -user roles. 
Technical Constraints: 
Local storage size limitaƟ ons (~5MB).
No cloud synchronizaƟ on or server-side processing. 
Basic security model with no encrypƟ on.
Future PotenƟ al & Proposed Enhancements
Proposed Enhancements: 
 MulƟ -currency support to cater to businesses with internaƟ onal transacƟ ons.
 PDF report generaƟ on for financial and sales reports.
 Inventory alerts for low stock levels. 
 Data export/import funcƟ onality (CSV/Excel).
 Chart visualizaƟ ons for financial and sales trends.
 MulƟ -user collaboraƟ on for business teams.
 Offline-first capabiliƟ es for uninterrupted business operaƟ ons.
 Expansion Areas: 
 Expense tracking module. 
 Customer relaƟ onship management (CRM) integraƟ on.
 Supplier management system. 
 Tax calculaƟ on system.
 Barcode scanning integraƟ on for improved inventory management.
Target Audience 
 Kenyan small business owners. 
 Solo entrepreneurs and retail store managers. 
 Startup founders and business students learning operaƟ ons and management. 
DESIGN 
Key RelaƟ onships: 
1. UI ↔ ApplicaƟ on Layer: 
- Event-driven interacƟ ons 
- Data binding for real-Ɵ me updates 
Figure 1 Pseudocode 
Figure 2 Class 
Figure 3 Design 
Figure 4 Use Case 
- ValidaƟ on feedback loop 
2. ApplicaƟ on ↔ Data Layer: 
- CRUD operaƟ ons 
- TransacƟ onal updates 
- Data synchronizaƟ on 
3. Cross-Layer Dependencies: 
- Security: Auth Controller ↔ Users DB 
- Inventory ↔ Sales: Cost price resoluƟ on 
- History ↔ AnalyƟ cs: Trend data sourcing 
Figure 5 LAYOUT
 
4. External IntegraƟ ons: 
- ParƟ cle animaƟ on via Canvas 
- Font loading from Google CDN 
- Profile image file handling 
 
TESTING 
 Test Overview 
The tests validate the core funcƟ onaliƟ es of the applicaƟ on, including user account 
management, inventory handling, sales tracking, data persistence, and UI feedback. The goal is 
to ensure that input validaƟ on, user interacƟ ons, and data integrity are working correctly. 
1. User Account Handling 
1.1 User Signup Test 
Test ObjecƟ ve:
Ensure successful account creaƟ on and validaƟ on.
Test Steps:
 Enter valid user details (name, email, password, confirm password, profile picture). 
 Submit the form. 
Expected Outcome:
 Account created with success message. 
 User stored in local storage. 
Test Cases:
1. Valid Data Input:
o Expected result: Success message, user account created. 
2. Invalid Data Input (Missing Field):
o Expected result: Error message: "Please fill in all fields." 
3. Invalid Email Format:
o Expected result: Error message: "Enter a valid email address." 
4. Password Length/Format Check:
o Expected result: Error message: "Password: 8+ chars, uppercase, number." 
5. Password Mismatch:
o Expected result: Error message: "Passwords do not match." 
1.2 User Login Test 
Test ObjecƟ ve:
Verify that the login process works correctly. 
Test Steps:
 Enter valid credenƟ als (name, password).
 Submit the form. 
Expected Outcome:
 Successful login redirects to the dashboard. 
Test Cases:
1. Valid Login:
o Expected result: Success message, user redirected to the dashboard. 
2. Invalid Login:
o Expected result: Error message: "Invalid name or password." 
2. Inventory Management 
2.1 Adding Inventory Item Test 
Test ObjecƟ ve:
Verify proper inventory item addiƟ on with validaƟ on.
Test Steps:
 Enter item details (name, cost, price, quanƟ ty).
 Submit to add to inventory. 
Expected Outcome:
 Item added, total profit updated, inventory stored in local storage. 
Test Cases:
1. Valid Inventory Item:
o Expected result: Item added and displayed correctly. 
2. Missing Field:
o Expected result: Error message: "Please fill in all inventory fields." 
3. Invalid Number Input:
o Expected result: Error message for invalid input. 
2.2 Inventory History Test 
Test ObjecƟ ve:
Ensure that changes to inventory are logged. 
Test Steps:
 Add items and check history. 
Expected Outcome:
 History shows items with cost, price, quanƟ ty, and profit.
Test Cases:
1. Valid History Log:
o Expected result: Item appears in history with Ɵmestamp.
2. Empty History:
o Expected result: Message: "No inventory history available." 
3. Sales Management 
3.1 Adding Sale TransacƟ on Test
Test ObjecƟ ve:
Ensure correct addiƟ on of sales transacƟ ons.
Test Steps:
 Enter sale details (item name, quanƟ ty, sale price).
 Submit to add sale. 
Expected Outcome:
 Sale recorded, revenue and profit updated. 
Test Cases:
1. Valid Sale TransacƟ on:
o Expected result: TransacƟ on added, revenue/profit displayed.
2. Missing Field in Sale:
o Expected result: Error message: "Please fill in all sales fields." 
3. Invalid Input (Non-numeric):
o Expected result: Error message for invalid input. 
3.2 Sales History Test 
Test ObjecƟ ve:
Ensure proper recording of sales transacƟ ons in history.
Test Steps:
 Add transacƟ ons and check history.
Expected Outcome:
 Sales history shows correct details (item, quanƟ ty, price, profit).
Test Cases:
1. Valid Sales History:
o Expected result: TransacƟ on appears in history.
2. Empty Sales History:
o Expected result: Message: "No sales history available." 
4. Data Persistence (LocalStorage) 
4.1 LocalStorage Persistence Test 
Test ObjecƟ ve:
Verify that data is correctly stored and persists across sessions. 
Test Steps:
 Add user, inventory, and sale. 
 Refresh page or restart app. 
Expected Outcome:
 Data (user, inventory, sales) persists aŌ er refresh/restart.
Test Cases:
1. Data Persistence (User, Inventory, Sales):
o Expected result: Data remains intact aŌ er page refresh.
5. UI/UX Feedback 
5.1 Feedback Display Test 
Test ObjecƟ ve:
Ensure proper feedback messages for user acƟ ons.
Test Steps:
 Perform acƟ ons (signup, login, add inventory/sale).
 Observe feedback messages. 
Expected Outcome:
 Correct success or error messages with proper styling. 
Test Cases:
1. Success Message Display:
o Expected result: Success message styled correctly. 
2. Error Message Display:
o Expected result: Error message styled correctly. 
Conclusion 
The tests cover criƟ cal features of the applicaƟ on, validaƟ ng user management, inventory 
handling, sales transacƟ ons, data persistence, and UI feedback. Running these tests ensures the 
core funcƟ onaliƟ es are operaƟ onal, data is preserved across sessions, and the user experience 
is consistent and reliable. 
 
RelaƟ onships 
Table 2 ENTITY TABLE 
EnƟ ty Related To RelaƟ onship Type DescripƟ on 
User Inventory Item 1-to-Many Each user can create mulƟ ple inventory 
items 
User Sales 
TransacƟ on 
1-to-Many Each user records mulƟ ple sales 
transacƟ ons 
Inventory Item 
Sales 
Weak Reference Sales reference inventory items by 
name 
EnƟ ty Related To RelaƟ onship Type DescripƟ on 
TransacƟ on (no direct foreign key) 
Inventory Item Inventory 
History 
1-to-Many 
(Temporal) 
Every inventory change creates a 
historical log entry 
Sales 
TransacƟ on 
Sales History 1-to-Many 
(Temporal) 
Every sale creates an immutable 
historical record 
 
Data Flow RelaƟ onships 
 A[User] -->|Input| B(Forms) 
B--> C{ValidaƟ on} 
C-->|Valid| D[ApplicaƟ on Logic] 
C -->|Invalid| E[Error Feedback] 
D--> F[(Data Layer)] 
F --> G[Reports/UI Updates] 
G--> H[User] 
 D --> I[External Systems] 
Forms 
2.1 AuthenƟ caƟ on Forms 
Table 3: AUTHENTICATION TABLE 
Form Fields ValidaƟ on Rules 
Signup 
- Name 
- Email 
- Password 
- Confirm Password 
- Email format 
- Password: 8+ chars, 1 uppercase, 1 
number 
- Password match 
Form Fields ValidaƟ on Rules 
 - Profile Picture (OpƟ onal) 
Login - Name 
- Password 
- Non-empty fields 
- CredenƟ al verificaƟ on 
Table 4 OPEERATIONAL FORMS 
Form Fields Business Rules 
Add Inventory - Item Name 
- Cost Price (KSh) 
- Selling Price (KSh) 
- QuanƟ ty 
- Numeric > 0 
- Selling Price > Cost Price 
- Unique item names (case￾insensiƟ ve) 
Record Sale - Item Name 
- QuanƟ ty Sold 
- Sale Price (KSh) 
- Item must exist in inventory 
- QuanƟ ty ≤ available stock 
- Price ≥ inventory cost 
\ 
Table 5SECURITY CONSTRAINTS 
Aspect ImplementaƟ on 
Password Storage Simulated hashing (plaintext in localStorage - not producƟ on￾safe) 
Input SaniƟ zaƟ on Trim whitespace, escape HTML characters 
Session Management Client-side "logged-in" state (no JWT/cookies) 
 
Constraints 
Table 6 INPUT CONSTRAINTS 
Constraint Type Examples 
Data Type - Prices: Numeric 
- QuanƟ ty: Integer 
23 | P a g e
Range - Cost Price > 0 
- Sale Price ≥ Inventory Cost 
ReferenƟ al Integrity - Sales items must exist in 
inventory 
Uniqueness - Unique email for signup 
- Case-insensiƟ ve unique item 
names 
2.2 Business Rules 
Table 7 BUSINESS RULES 
Rule ImplementaƟ on 
Profit CalculaƟ on Profit = (Sale Price - Inventory Cost) * QuanƟ ty Sold 
Inventory DepleƟ on Sales reduce available stock (implied, not enforced in current 
version) 
Historical Immutability Inventory/Sales history cannot be modified aŌ er creaƟ on 
2.3 System Constraints 
Table 8 SYSTEM CONTRAINTS 
Constraint Impact 
localStorage Size Limit (~5MB) Limits historical data retenƟ on 
Browser Security Policies Profile images stored as Base64 strings (no file system 
access) 
Client-Side Only No data persistence across devices 
 
Advanced Constraints & Relationships 5.1 Cross-Entity Validation
javascript 
// Sales → Inventory Dependency funcƟ on 
validateSale(itemName, quanƟ ty) { const inventoryItem 
= inventory.find(item => item.itemName.toLowerCase() 
=== itemName.toLowerCase() 
 ); 
 
 return inventoryItem && inventoryItem.quanƟ ty >= quanƟ ty; 
} 
Temporal RelaƟ onships 
• Inventory History: Tracks state changes over Ɵme (price adjustments, stock 
updates) 
• Sales History: Maintains immutable records for audiƟ ng 
Table 9:FUTURE REPORT EXTENSION 
Report Type PotenƟ al ImplementaƟ on 
Inventory Aging Track stock duraƟ on to idenƟ fy slow-moving items 
Customer SegmentaƟ on Group sales by customer type (requires CRM 
integraƟ on) 
Tax Reports VAT calculaƟ ons and filing-ready formats 
 
Database Table DefiniƟ ons
1. Users Table (Core EnƟ ty)
sql 
CopyEdit 
CREATE TABLE Users ( 
 UserID TEXT PRIMARY KEY, -- UUID for unique identification 
 Name TEXT NOT NULL, 
 Email TEXT UNIQUE NOT NULL, -- Email must be case-insensitive and 
unique 
 Password TEXT NOT NULL, -- Password (simulated hash in current 
version) 
 ProfilePicture BLOB -- Base64 encoded image (nullable) 
); 
2. Inventory Items Table (1:M with Users) 
sql 
CopyEdit 
CREATE TABLE InventoryItems ( 
 ItemID TEXT PRIMARY KEY, -- UUID for unique identification 
 UserID TEXT NOT NULL REFERENCES Users(UserID) ON DELETE CASCADE, -- 
Foreign key for user 
 ItemName TEXT NOT NULL, -- Unique per user (case-insensitive) 
 CostPrice DECIMAL(10,2) NOT NULL CHECK(CostPrice > 0), -- Positive cost 
price constraint 
 SellingPrice DECIMAL(10,2) NOT NULL CHECK(SellingPrice > CostPrice), -- 
Selling price must be greater than cost 
 Quantity INTEGER NOT NULL CHECK(Quantity >= 0), -- Quantity must be non￾negative 
 Timestamp DATETIME NOT NULL, -- Timestamp for tracking inventory 
entry time 
 UNIQUE (UserID, LOWER(ItemName)) -- Case-insensitive uniqueness 
); 
3. Sales TransacƟ ons Table (1:M with Users)
sql 
CopyEdit 
CREATE TABLE SalesTransactions ( 
 SaleID TEXT PRIMARY KEY, -- UUID for unique identification 
 UserID TEXT NOT NULL REFERENCES Users(UserID) ON DELETE CASCADE, -- 
Foreign key for user 
 ItemName TEXT NOT NULL, -- Item name from Inventory 
(denormalized) 
 QuantitySold INTEGER NOT NULL CHECK(QuantitySold > 0), -- Quantity sold 
must be positive 
 SalePrice DECIMAL(10,2) NOT NULL CHECK(SalePrice >= ( 
 SELECT CostPrice 
 FROM InventoryItems 
 WHERE UserID = SalesTransactions.UserID 
 AND LOWER(ItemName) = LOWER(SalesTransactions.ItemName) 
 )), -- Sale price must be at least cost price 
 Timestamp DATETIME NOT NULL -- Timestamp of the sale 
); 
25 | P a g e
4. Inventory History Table (Temporal 1:M with InventoryItems) 
sql 
CopyEdit 
CREATE TABLE InventoryHistory ( 
 HistoryID TEXT PRIMARY KEY, -- UUID for unique identification 
 ItemID TEXT NOT NULL REFERENCES InventoryItems(ItemID) ON DELETE CASCADE, 
-- Foreign key for inventory item 
 CostPrice DECIMAL(10,2) NOT NULL, 
 SellingPrice DECIMAL(10,2) NOT NULL, 
 Quantity INTEGER NOT NULL, -- Quantity in the historical entry 
 Timestamp DATETIME NOT NULL -- Timestamp for historical data 
); 
5. Sales History Table (Temporal 1:M with SalesTransacƟ ons)
sql 
CopyEdit 
CREATE TABLE SalesHistory ( 
 HistoryID TEXT PRIMARY KEY, -- UUID for unique identification 
 SaleID TEXT NOT NULL REFERENCES SalesTransactions(SaleID) ON DELETE 
CASCADE, -- Foreign key for sale 
 ItemName TEXT NOT NULL, -- Historical item name for sale 
tracking 
 QuantitySold INTEGER NOT NULL, 
 SalePrice DECIMAL(10,2) NOT NULL, 
 Timestamp DATETIME NOT NULL -- Timestamp for sales history record 
); 
Indexes for Common Queries 
sql 
CopyEdit 
CREATE INDEX idx_inventory_user_item ON InventoryItems(UserID, 
LOWER(ItemName)); 
CREATE INDEX idx_sales_user_item ON SalesTransactions(UserID, 
LOWER(ItemName)); 
CREATE INDEX idx_inv_history ON InventoryHistory(ItemID, Timestamp); 
CREATE INDEX idx_sales_history ON SalesHistory(SaleID, Timestamp); 
ReferenƟ al Integrity PaƩ erns
Manual Cascade Delete (for Users and Related Data) 
js 
CopyEdit 
function deleteUser(userId) { 
 // Delete related inventory and sales records for the user 
 deleteInventoryForUser(userId); 
 deleteSalesForUser(userId); 
 deleteFromStorage('Users', userId); // Deletes user from Users table 
} 
Sales Price ValidaƟ on FuncƟ on
js 
CopyEdit 
function validateSalePrice(userId, itemName, salePrice) { 
 const item = inventory.find(i => 
 i.UserID === userId && 
 i.ItemName.toLowerCase() === itemName.toLowerCase() 
 ); 
 return item && salePrice >= item.CostPrice; // Ensure sale price is 
greater than or equal to cost price 
} 
Temporal Table RelaƟ onships
1. Inventory Items (Current State) 
 The InventoryItems table represents the current state of the inventory items. 
o RelaƟ onship: One-to-many with InventoryHistory (past states). 
o AcƟ on: Insert-only operaƟ ons in InventoryHistory to maintain historical data. 
2. Sales TransacƟ ons (Base Record)
 The SalesTransactions table contains the base records for sales transacƟ ons.
o RelaƟ onship: One-to-many with SalesHistory (immutable copy). 
o AcƟ on: Use ON CREATE trigger to simulate historical data logging in 
SalesHistory. 
DenormalizaƟ on Strategy
 SalesTransacƟ ons.ItemName: Stores a snapshot of the item name as a denormalized 
field to reduce joins. 
 SalesHistory: Contains complete sales context, including item details (denormalized) to 
avoid unnecessary joins for historical data analysis. 
Check Constraint Workarounds (SQLite LimitaƟ ons)
Simulated Check Constraints in App Logic 
For operaƟ ons where database constraints are not supported (like CHECK constraints in SQLite 
when using localStorage), perform validaƟ on in applicaƟ on logic:
js 
CopyEdit 
// Simulate CHECK constraints for inventory validation 
function addInventoryItem(item) { 
27 | P a g e
 if (item.SellingPrice <= item.CostPrice) { 
 throw new Error('Selling price must exceed cost price'); 
 } 
 // Continue with adding the item logic... 
} 
TABLES 
/****** Users Table (Core EnƟ ty) ******/ 
CREATE TABLE Users ( 
 UserID TEXT NOT NULL PRIMARY KEY /* UUID */ 
 CHECK (LENGTH(UserID) = 36), 
 Name TEXT NOT NULL 
 CHECK (LENGTH(Name) BETWEEN 2 AND 100), 
 Email TEXT NOT NULL UNIQUE /* Case-insensiƟ ve */ 
 CHECK (Email LIKE '%@%._%'), 
 Password TEXT NOT NULL /* Would be hashed in producƟ on */ 
 CHECK (LENGTH(Password) >= 8), 
 ProfilePicture BLOB /* Nullable */ 
 DEFAULT NULL, 
 CreatedAt DATETIME NOT NULL 
 DEFAULT CURRENT_TIMESTAMP 
); 
 
/****** Inventory Items Table ******/ 
CREATE TABLE InventoryItems ( 
 ItemID TEXT NOT NULL PRIMARY KEY /* UUID */ 
 CHECK (LENGTH(ItemID) = 36), 
 UserID TEXT NOT NULL 
 REFERENCES Users(UserID) ON DELETE CASCADE, 
29 | P a g e
 ItemName TEXT NOT NULL 
 CHECK (LENGTH(ItemName) BETWEEN 1 AND 100), 
 CostPrice DECIMAL(10,2) NOT NULL 
 CHECK (CostPrice > 0), 
 SellingPrice DECIMAL(10,2) NOT NULL 
 CHECK (SellingPrice > CostPrice), 
 QuanƟ ty INTEGER NOT NULL 
 DEFAULT 0 
 CHECK (QuanƟ ty >= 0), 
 LastUpdated DATETIME NOT NULL 
 DEFAULT CURRENT_TIMESTAMP, 
 
 /* Case-insensiƟ ve unique constraint per user */ 
 UNIQUE (UserID, LOWER(ItemName)) 
); 
 
/****** Sales TransacƟ ons Table ******/ 
CREATE TABLE SalesTransacƟ ons ( 
 SaleID TEXT NOT NULL PRIMARY KEY /* UUID */ 
 CHECK (LENGTH(SaleID) = 36), 
 UserID TEXT NOT NULL 
 REFERENCES Users(UserID) ON DELETE CASCADE, 
 ItemName TEXT NOT NULL /* Denormalized name */ 
 CHECK (LENGTH(ItemName) BETWEEN 1 AND 100), 
 QuanƟ tySold INTEGER NOT NULL 
 CHECK (QuanƟ tySold > 0), 
 SalePrice DECIMAL(10,2) NOT NULL 
 CHECK (SalePrice > 0), 
 SaleTimestamp DATETIME NOT NULL 
 DEFAULT CURRENT_TIMESTAMP, 
 
 /* Cross-table validaƟ on (would need trigger in real DB) */ 
 CHECK (SalePrice >= ( 
 SELECT CostPrice 
 FROM InventoryItems 
 WHERE UserID = SalesTransacƟ ons.UserID 
 AND LOWER(ItemName) = LOWER(SalesTransacƟ ons.ItemName) 
 )) 
); 
 
/****** Inventory History Table ******/ 
CREATE TABLE InventoryHistory ( 
 HistoryID TEXT NOT NULL PRIMARY KEY /* UUID */ 
 CHECK (LENGTH(HistoryID) = 36), 
 ItemID TEXT NOT NULL 
 REFERENCES InventoryItems(ItemID) ON DELETE CASCADE, 
 CostPrice DECIMAL(10,2) NOT NULL 
 CHECK (CostPrice > 0), 
 SellingPrice DECIMAL(10,2) NOT NULL 
 CHECK (SellingPrice > CostPrice), 
 QuanƟ ty INTEGER NOT NULL 
 CHECK (QuanƟ ty >= 0), 
31 | P a g e
 RecordedAt DATETIME NOT NULL 
 DEFAULT CURRENT_TIMESTAMP 
); 
 
/****** Sales History Table ******/ 
CREATE TABLE SalesHistory ( 
 HistoryID TEXT NOT NULL PRIMARY KEY /* UUID */ 
 CHECK (LENGTH(HistoryID) = 36), 
 SaleID TEXT NOT NULL 
 REFERENCES SalesTransacƟ ons(SaleID) ON DELETE CASCADE, 
 ItemName TEXT NOT NULL 
 CHECK (LENGTH(ItemName) BETWEEN 1 AND 100), 
 QuanƟ tySold INTEGER NOT NULL 
 CHECK (QuanƟ tySold > 0), 
 SalePrice DECIMAL(10,2) NOT NULL 
 CHECK (SalePrice > 0), 
 RecordedAt DATETIME NOT NULL 
 DEFAULT CURRENT_TIMESTAMP 
); 
 
Key RelaƟ onships Diagram 
Users 
└──1:M── InventoryItems (UserID) 
│ └──1:M── InventoryHistory (ItemID) 
│ 
└──1:M── SalesTransac ons (UserID) 
 └──1:1── SalesHistory (SaleID) 
Constraint Summary 
1. Primary Keys o All tables use UUIDs 
with length validaƟ on o Format check: 
CHECK (LENGTH(ID) = 36) 
2. Foreign Keys o ON DELETE CASCADE for all 
relaƟ onships o User deleƟ on removes 
all related records 
3. Nullability o Only Users.ProfilePicture 
allows NULL o All other columns are NOT 
NULL 
4. Default Values o Timestamps: DEFAULT 
CURRENT_TIMESTAMP o Inventory 
quanƟ ty: DEFAULT 0 
5. Business Logic Constraints 
Inventory: 
- SellingPrice > CostPrice 
- QuanƟ ty ≥ 0 
 
Sales: 
- SalePrice ≥ Inventory.CostPrice 
- QuanƟ tySold > 0 
 
Users: 
33 | P a g e
- Password length ≥ 8 
- Valid email format 
ImplementaƟ on Notes 
1. Case-InsensiƟ ve Matching o Enforced via 
LOWER() in unique constraints o Example: 
UNIQUE (UserID, LOWER(ItemName)) 
2. Temporal Tables o InventoryHistory tracks 
state changes 
o SalesHistory preserves immutable records 
3. DenormalizaƟ on o SalesTransacƟ ons 
stores ItemName copy o Ensures 
historical accuracy if items renamed 
4. Simulated Triggers // ApplicaƟ on-layer trigger 
example funcƟ on createSale(sale) { 
validateSalePrice(sale); // CHECK constraint 
simulaƟ on addToSalesHistory(sale); // 
Temporal record 
} 
 
DOMAIN CONSTRAINTS 
Table 10: DOMAIN CONSTRAINTS 
Table Column Constraint 
Users UserID UUID format (36-character string) 
 Email Valid email format (LIKE '%@%._%') 
 Password Minimum 8 characters 
InventoryItems ItemName 1-100 characters 
 CostPrice DECIMAL(10,2) > 0 
 SellingPrice DECIMAL(10,2) > CostPrice 
Table Column Constraint 
 QuanƟ ty INTEGER ≥ 0 
SalesTransacƟ ons QuanƟ tySold INTEGER > 0 
 SalePrice DECIMAL(10,2) ≥ 
InventoryItems.CostPrice 
All Tables Timestamp columns Valid dateƟ me format 
 
1. ReferenƟ al Integrity Rules 
RelaƟ onship Rule 
InventoryItems.UserID → Users.UserID ON DELETE CASCADE (Delete inventory when user 
is deleted) 
35 | P a g e
SalesTransacƟ ons.UserID → Users.UserID ON DELETE CASCADE (Delete sales when user is 
deleted) 
InventoryHistory.ItemID → 
InventoryItems.ItemID 
ON DELETE CASCADE (Delete history when item is 
removed) 
SalesHistory.SaleID → 
SalesTransacƟ ons.SaleID 
ON DELETE CASCADE (Delete history when sale is 
removed) 
 
2. Key ValidaƟ ons 
ValidaƟ on ImplementaƟ on 
Case-InsensiƟ ve Uniqueness UNIQUE (UserID, LOWER(ItemName)) (InventoryItems) 
Inventory-Sales Sync SalePrice ≥ InventoryItems.CostPrice (ApplicaƟ on-layer trigger) 
Stock Availability QuanƟ tySold ≤ InventoryItems.QuanƟ ty (Enforced in business 
logic) 
ValidaƟ on ImplementaƟ on 
Historical Immutability History tables allow INSERT only (No UPDATE/DELETE) 
Password Complexity Minimum 8 chars + 1 uppercase + 1 number (ApplicaƟ on-layer 
check) 
 
3. CriƟ cal AsserƟ ons 
-- AsserƟ on 1: No orphaned inventory items 
CREATE ASSERTION NoOrphanedInventory 
CHECK (NOT EXISTS ( 
 SELECT 1 FROM InventoryItems 
 LEFT JOIN Users USING (UserID) 
 WHERE Users.UserID IS NULL 
)); 
 
-- AsserƟ on 2: PosiƟ ve profit margin 
CREATE ASSERTION PosiƟ veProfitMargin 
CHECK (NOT EXISTS ( 
 SELECT 1 FROM SalesTransacƟ ons 
 WHERE SalePrice < ( 
 SELECT CostPrice 
 FROM InventoryItems 
 WHERE UserID = SalesTransacƟ ons.UserID 
 AND LOWER(ItemName) = LOWER(SalesTransacƟ ons.ItemName) 
)); 
 
-- AsserƟ on 3: Temporal consistency 
CREATE ASSERTION ValidHistoryTimestamps 
CHECK (NOT EXISTS ( 
 SELECT 1 FROM InventoryHistory ih 
 JOIN InventoryItems i USING (ItemID) 
 WHERE ih.RecordedAt < i.LastUpdated 
)); 
5. Cross-Table ValidaƟ on Logic 
Inventory-Sales QuanƟ ty Check 
37 | P a g e
(Enforced via applicaƟ on logic due to localStorage 
limitaƟ ons) funcƟ on recordSale(itemName, quanƟ ty) { 
const inventoryItem = inventory.find(i => 
 i.ItemName.toLowerCase() === itemName.toLowerCase() && 
 i.UserID === currentUser.UserID 
 ); 
 
 if (!inventoryItem || inventoryItem.QuanƟ ty < quanƟ ty) { 
throw new Error("Insufficient stock"); 
 } 
 
 // Proceed with sale recording 
inventoryItem.QuanƟ ty -= quanƟ ty; 
} 
. Data Integrity Matrix 
Table 11 DATA INTEGRITY 
Integrity Type Examples 
EnƟ ty Integrity All primary keys are non-NULL and unique 
ReferenƟ al Integrity No dangling foreign keys (enforced via ON DELETE CASCADE) 
Domain Integrity Prices > 0, valid email formats 
Integrity Type Examples 
User-Defined Integrity SellingPrice > CostPrice, case-insensiƟ ve unique item names per 
user 
 
 
Table 12 HISTORY DATA 
Rule Enforcement Mechanism 
Inventory Change Tracking Trigger on InventoryItems updates → Insert into 
InventoryHistory 
Sale FinalizaƟ on Insert into SalesHistory on sale creaƟ on 
Temporal Query Support History tables include Ɵmestamps for Ɵme-based analysis 
Immutable Records No UPDATE/DELETE allowed on history tables 
 
ImplementaƟ on ConsideraƟ ons 
1. Client-Side LimitaƟ ons o Simulated triggers via applicaƟ on 
logic o Manual constraint checks (e.g., SalePrice ≥ 
CostPrice) o No transacƟ on support (atomicity handled per 
operaƟ on) 
2. Performance OpƟ mizaƟ ons o Indexes on frequently 
queried columns: 
CREATE INDEX idx_user_items ON InventoryItems(UserID, LOWER(ItemName)); 
CREATE INDEX idx_sales_dates ON SalesTransacƟ ons(SaleTimestamp); 
3. Data ValidaƟ on Workflow 
 User Input → UI Valida on → Applica on Logic → Database Checks → Storage 
 
Project Report: Entrepreneur's Diary System 
Project Overview 
The Entrepreneur's Diary system is designed to help small-scale entrepreneurs manage their 
business operaƟ ons efficiently. The applicaƟ on enables users to track inventory, record sales 
transacƟ ons, calculate profits, and manage customer payments. The goal is to provide an 
intuiƟ ve plaƞ orm for entrepreneurs to monitor and streamline their business acƟ viƟ es, allowing 
them to make informed decisions and improve overall business efficiency. 
Project ObjecƟ ves
User Management: Allow users to register, login, and manage their profiles securely. 
Inventory Management: Enable users to add, update, and track inventory items with detailed 
pricing and quanƟ ty informaƟ on.
Sales TransacƟ ons: Track sales with specific item details, quanƟƟ es, and prices.
Profit CalculaƟ on: Provide real-Ɵ me profit data, including daily, single-sale, and grand (lifeƟ me) 
profits. 
Payment Tracking: Track customer payments through integraƟ on with M-Pesa or other payment 
systems. 
User Interface: Provide a clean, modern, and user-friendly interface to ensure ease of use. 
Technologies Used 
Frontend: 
HTML for structuring the web pages. 
CSS for styling and creaƟ ng a visually appealing interface.
JavaScript for interacƟ ve elements and dynamic funcƟ onality.
Backend: 
Python for server-side logic and processing. 
SQLite for lightweight database management. 
Other Technologies: 
MongoDB for user authenƟ caƟ on and profile management.
System Architecture 
The system consists of several key components, each serving a specific funcƟ on:
User AuthenƟ caƟ on: The system supports user registraƟ on and login, with profile management. 
Secure authenƟ caƟ on ensures that only the registered user can access their specific data.
Inventory Management: Inventory items are stored with aƩ ributes like cost price, selling price, 
and quanƟ ty. The system allows adding new items, updaƟ ng quanƟƟ es, and viewing current 
stock levels. 
Sales TransacƟ ons: Sales data is captured with transacƟ on details such as item name, quanƟ ty 
sold, sale price, and the Ɵme of the transacƟ on. This allows users to track their revenue.
Profit CalculaƟ on: The system calculates and displays profits in real-Ɵ me, showing daily, per￾sale, and lifeƟ me profits.
Payment IntegraƟ on: A payment tracking system (e.g., M-Pesa) is incorporated to log customer 
payments, allowing the user to track outstanding balances. 
Database Design 
39 | P a g e
The database is designed with scalability and integrity in mind. Key enƟƟ es and relaƟ onships are 
as follows: 
Users Table: Stores user informaƟ on such as name, email, and password (hashed).
InventoryItems Table: Stores item details like cost price, selling price, quanƟ ty, and Ɵmestamps.
SalesTransacƟ ons Table: Records sales data with item details, sale price, and quanƟ ty.
InventoryHistory Table: Keeps track of historical changes in inventory (e.g., price changes, 
quanƟ ty updates).
SalesHistory Table: Keeps a record of historical sales for audiƟ ng and analysis.
SQL Schema: 
sql 
CopyEdit 
CREATE TABLE Users ( 
 UserID TEXT PRIMARY KEY, 
 Name TEXT NOT NULL, 
 Email TEXT UNIQUE NOT NULL, 
 Password TEXT NOT NULL, 
 ProfilePicture BLOB 
); 
CREATE TABLE InventoryItems ( 
 ItemID TEXT PRIMARY KEY, 
 UserID TEXT NOT NULL REFERENCES Users(UserID) ON DELETE CASCADE, 
 ItemName TEXT NOT NULL, 
 CostPrice DECIMAL(10,2) NOT NULL CHECK(CostPrice > 0), 
 SellingPrice DECIMAL(10,2) NOT NULL CHECK(SellingPrice > CostPrice), 
 QuanƟ ty INTEGER NOT NULL CHECK(QuanƟ ty >= 0), 
 Timestamp DATETIME NOT NULL, 
 UNIQUE (UserID, LOWER(ItemName)) 
); 
CREATE TABLE SalesTransacƟ ons (
 SaleID TEXT PRIMARY KEY, 
 UserID TEXT NOT NULL REFERENCES Users(UserID) ON DELETE CASCADE, 
 ItemName TEXT NOT NULL, 
 QuanƟ tySold INTEGER NOT NULL CHECK(QuanƟ tySold > 0), 
 SalePrice DECIMAL(10,2) NOT NULL CHECK(SalePrice >= ( 
 SELECT CostPrice 
 FROM InventoryItems 
 WHERE UserID = SalesTransacƟ ons.UserID 
 AND LOWER(ItemName) = LOWER(SalesTransacƟ ons.ItemName)
 )), 
 Timestamp DATETIME NOT NULL 
); 
System Features 
1. User RegistraƟ on & AuthenƟ caƟ on
Users can register by providing their name, email, and password. 
AŌ er registraƟ on, a confirmaƟ on email is sent, and users must verify their email to finalize 
registraƟ on.
The login system ensures only authorized users can access their data. 
2. Inventory Management 
Users can add, update, or delete inventory items. 
Each item is tracked with a cost price, selling price, and quanƟ ty.
The system ensures that the selling price is always greater than the cost price. 
Users can view a list of their inventory items and their current stock levels. 
3. Sales TransacƟ on Tracking
Sales transacƟ ons are logged with item names, quanƟƟ es sold, and sale prices.
Each sale is Ɵmestamped for historical tracking.
The system calculates profits based on the sale price and cost price of items sold. 
4. Profit CalculaƟ on
The system calculates three types of profits: 
Single Sale Profit: Profit from individual transacƟ ons.
Daily Profit: Total profit made in a given day. 
Grand Profit: Total profit since account creaƟ on.
5. Payment Tracking 
The M-Pesa Fetch feature tracks payments made by customers, helping users track outstanding 
balances. 
Challenges and SoluƟ ons
Data Integrity: 
Ensuring the integrity of user data was a key challenge, especially with sales transacƟ ons linked 
to inventory items. We used foreign keys to maintain referenƟ al integrity.
SoluƟ on: We implemented cascading deletes to remove related sales and inventory items when 
a user is deleted from the system. 
Concurrency: 
Managing simultaneous updates to inventory and sales transacƟ ons was challenging.
SoluƟ on: We implemented proper locking mechanisms and handled race condiƟ ons in the 
backend code to ensure the consistency of data. 
User Interface: 
Designing a UI that is both funcƟ onal and aƩ racƟ ve was challenging, parƟ cularly when 
integraƟ ng dynamic data like inventory levels and sales transacƟ ons.
SoluƟ on: We used modern CSS and JavaScript to create an interacƟ ve, visually appealing 
interface. The design prioriƟ zes usability while ensuring ease of navigaƟ on.
Future Enhancements 
Mobile App: Developing a mobile version of the applicaƟ on to allow users to manage their 
business on-the-go. 
41 | P a g e
Advanced ReporƟ ng: Adding features for generaƟ ng detailed reports on sales, inventory, and 
profits, along with export opƟ ons to CSV or PDF.
IntegraƟ on with More Payment Systems: IntegraƟ ng addiƟ onal payment gateways for broader 
customer reach. 
Conclusion 
The Entrepreneur's Diary system is a funcƟ onal and scalable soluƟ on for small-scale 
entrepreneurs to manage their business operaƟ ons. By focusing on core features like inventory 
management, sales tracking, and profit calculaƟ on, the system streamlines daily operaƟ ons and 
provides valuable insights for business growth. The project was built with a focus on simplicity, 
efficiency, and user experience, ensuring that entrepreneurs can manage their businesses with 
minimal effort and maximum effecƟ veness.
Prepared By: 
Jay Alchemist 
SoŌ ware Engineer
MessiahTechSoluƟ ons Inc.
REFERENCES 
References:
 HTML Forms and ValidaƟ on
HTML Form Elements – MDN Web Docs
Input ValidaƟ on in HTML Forms – MDN Web Docs
 Local Storage API
Web Storage: LocalStorage – MDN Web Docs Local storage is used to persist user data 
(e.g., user accounts) across page refreshes. 
1.2 User Login Test 
References:
 AuthenƟ caƟ on Methods
Client-Side AuthenƟ caƟ on with JavaScript – MDN Web Docs
Login is typically handled using local storage to persist user session data. 
 Password Hashing and Security
Client-Side Password Hashing with JavaScript – OWASP Cheat Sheet 
Ensure secure handling of passwords by employing hashing techniques (e.g., bcrypt or 
Argon2) in real applicaƟ ons.
2. Inventory Management 
2.1 Adding Inventory Item Test 
References:
 Form ValidaƟ on for Inventory
ValidaƟ ng Numbers and Text in Forms – MDN Web Docs
ValidaƟ on ensures that input data (cost, price, and quanƟ ty) is correctly formaƩ ed.
 Local Storage for Inventory
Using Local Storage for Inventory Management – JavaScript.info 
Inventory data is stored in local storage to maintain state across page reloads. 
2.2 Inventory History Test 
References:
 Logging with Timestamps
Working with JavaScript Date Objects – 
SCREENSHOTS 
Figure 6 dashboard 
43 | P a g e
Figure 7: inventory history 
Figure 8 inventory management 
Figure 9 sales history 
Figure 10 sales management 
Figure 11 sign up form 
Figure 12 login form 
CONCLUSION 
This project successfully defines and implements the core funcƟ onaliƟ es necessary for an 
effecƟ ve entrepreneurial management system. The tesƟ ng phase, outlined in the 
documentaƟ on, ensures that key features such as user account handling, inventory 
management, sales tracking, data persistence, and UI/UX feedback are thoroughly validated. 
By applying the principles of local storage for data persistence, proper input validaƟ on, and 
clear user feedback mechanisms, the applicaƟ on is built to be robust, user-friendly, and 
scalable. The tests not only ensure the accuracy of data handling but also guarantee a smooth 
user experience, ensuring users can efficiently manage their business operaƟ ons, track profits, 
and handle sales transacƟ ons.
The inclusion of detailed references to best pracƟ ces in tesƟ ng, UI design, and local storage 
management ensures that the project adheres to modern web development standards. 
Furthermore, by focusing on user-centered design, the project remains adaptable for future 
improvements and expansion, such as the potenƟ al creaƟ on of mobile and desktop 
applicaƟ ons.
This foundaƟ onal work lays the groundwork for a dynamic and scalable system that aligns with 
the needs of entrepreneurs, ensuring ease of use, data integrity, and seamless operaƟ on. 
45 | P a g e
Moving forward, the project can be expanded with addiƟ onal features and a mobile-friendly 
interface to further enhance its uƟ lity and user base.
REFERENCES 
References:
 HTML Forms and ValidaƟ on
HTML Form Elements – MDN Web Docs
Input ValidaƟ on in HTML Forms – MDN Web Docs
 Local Storage API
Web Storage: LocalStorage – MDN Web Docs Local storage is used to persist user data 
(e.g., user accounts) across page refreshes. 
1.2 User Login Test 
References:
 AuthenƟ caƟ on Methods
Client-Side AuthenƟ caƟ on with JavaScript – MDN Web Docs
Login is typically handled using local storage to persist user session data. 
 Password Hashing and Security
Client-Side Password Hashing with JavaScript – OWASP Cheat Sheet 
Ensure secure handling of passwords by employing hashing techniques (e.g., bcrypt or 
Argon2) in real applicaƟ ons.
2. Inventory Management 
2.1 Adding Inventory Item Test 
References:
 Form ValidaƟ on for Inventory
ValidaƟ ng Numbers and Text in Forms – MDN Web Docs
ValidaƟ on ensures that input data (cost, price, and quanƟ ty) is correctly formaƩ ed.
 Local Storage for Inventory
Using Local Storage for Inventory Management – JavaScript.info 
Inventory data is stored in local storage to maintain state across page reloads. 
2.2 Inventory History Test 
References:
 Logging with Timestamps
Working with JavaScript Date Objects – MDN Web Docs
The inventory history logs Ɵmestamps to track changes to the inventory.
3. Sales Management 
3.1 Adding Sale TransacƟ on Test
References:
 Handling Sale TransacƟ ons
Handling Forms with JavaScript – MDN Web Docs
Validates inputs for sales transacƟ ons, ensuring the data (item name, price, and 
quanƟ ty) is valid before submission.
 Local Storage for Sales Tracking
Storing Sales TransacƟ ons in Local Storage – W3Schools 
Sales data is stored and tracked in local storage for easy retrieval. 
3.2 Sales History Test 
References:
 Displaying Sales History
Rendering Data from LocalStorage – JavaScript.info 
Sales history is retrieved from local storage and displayed with relevant details. 
4. Data Persistence (LocalStorage) 
4.1 LocalStorage Persistence Test 
References:
 Data Persistence with Local Storage
Web Storage API – LocalStorage – MDN Web Docs
LocalStorage allows for data persistence between sessions, making it ideal for saving 
user and inventory data without requiring a backend database. 
47 | P a g e
 Session Management
Managing Sessions in Client-Side JavaScript – MDN Web Docs
This secƟ on explains the use of LocalStorage and SessionStorage for managing data 
persistence in web applicaƟ ons.
5. UI/UX Feedback 
5.1 Feedback Display Test 
References:
 CSS for Feedback Styling
Styling Success and Error Messages – CSS-Tricks 
CSS is used to ensure that feedback messages (success/error) are displayed with the 
correct style, ensuring clarity for the user. 
 User Interface Design Principles
Principles of UX/UI Design – UX Design 
Understanding how feedback should be communicated to users is criƟ cal for building an 
intuiƟ ve and user-friendly interface. 
General References 
JavaScript TesƟ ng Frameworks
 Jest TesƟ ng Framework
Jest DocumentaƟ on – Jest Official Site
Jest is widely used for tesƟ ng JavaScript applicaƟ ons, including user input validaƟ on, 
local storage manipulaƟ on, and form submissions.
 Mocha TesƟ ng Framework
Mocha DocumentaƟ on – Mocha Official Site
Mocha is another widely used JavaScript tesƟ ng framework that integrates well with 
asserƟ on libraries like Chai for validaƟ on.
Test-Driven Development (TDD) 
 Test-Driven Development in JavaScript
Test-Driven Development (TDD) Explained – JavaScript.info 
This guide explains the concept of TDD, which can be applied when wriƟ ng tests for 
features like user sign-up, inventory management, and sales transacƟ ons.
LocalStorage Best PracƟ ces
 LocalStorage and Security Best PracƟ ces
Best PracƟ ces for Using LocalStorage – OWASP Secure Coding Guidelines 
LocalStorage should be used carefully to store sensiƟ ve data. It’s important to avoid 
storing unencrypted sensiƟ ve informaƟ on in local storage.
 
49 | P a g e
