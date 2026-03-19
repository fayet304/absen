# Sistem Absensi Karyawan

A comprehensive Employee Attendance System built with Next.js 16, TypeScript, Tailwind CSS, and Prisma.

## 🚀 Features

### 1. Login System
- Username & password authentication
- Role-based access (Admin & Karyawan)
- Session persistence

### 2. Dashboard
- Real-time clock display
- Today's status badge (Belum Absen / Sedang Bekerja / Sedang Izin / Selesai)
- Clock in/out times
- Total work hours calculation
- Auto-refresh every 30 seconds

### 3. Attendance Features
- **Clock In** - Records time + GPS location (optional)
- **Clock Out** - Calculates total work hours minus break time
- **Break Management** - 6 default types:
  - Izin Kamar Mandi
  - Izin Ibadah
  - Izin Beli Makan
  - Izin Merokok
  - Istirahat 1
  - Istirahat 2

### 4. Admin Panel
- **Divisions** - Add/edit divisions
- **Employees** - Add users with role and division assignment
- **Work Schedules** - Configure shift times per division
- **Permission Types** - Add/activate/deactivate break types

### 5. Reports
- Filter by date range, employee, division
- Quick date presets (Today, Yesterday, This Week, This Month, Last Month)
- Statistics cards with real-time data
- Pagination support
- Export to CSV and Excel
- Summary by division and employee
- Late arrival and early departure indicators

## 🛠️ Tech Stack

- **Framework**: Next.js 16 with App Router
- **Language**: TypeScript 5
- **Styling**: Tailwind CSS 4 + shadcn/ui
- **Database**: Prisma ORM with SQLite
- **State Management**: Zustand
- **Icons**: Lucide React

## 📦 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/sistem-absensi.git
cd sistem-absensi
```

2. Install dependencies:
```bash
bun install
```

3. Set up the database:
```bash
bun run db:push
bun run prisma/seed.ts
```

4. Create `.env` file:
```env
DATABASE_URL="file:./db/custom.db"
```

5. Run the development server:
```bash
bun run dev
```

## 🔐 Default Credentials

| Role | Username | Password |
|------|----------|----------|
| Admin | admin | admin123 |
| Karyawan | karyawan1 | karyawan123 |

## 📁 Project Structure

```
├── prisma/
│   ├── schema.prisma      # Database schema
│   └── seed.ts            # Seed data
├── src/
│   ├── app/
│   │   ├── api/           # API routes
│   │   ├── page.tsx       # Main application
│   │   ├── layout.tsx     # Root layout
│   │   └── globals.css    # Global styles
│   ├── components/ui/     # shadcn/ui components
│   └── lib/
│       ├── db.ts          # Prisma client
│       └── auth-store.ts  # Zustand store
├── public/                # Static assets
└── package.json
```

## 🗄️ Database Schema

- **User** - Employees with username, password, name, role, division
- **Division** - Departments
- **WorkSchedule** - Shift schedules per division
- **PermissionType** - Customizable break types
- **Attendance** - Daily attendance records
- **Break** - Permission/break records

## 📝 License

MIT License
