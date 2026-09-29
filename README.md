# PulsePoint

PulsePoint is a Java desktop application for managing examinee health and profile information. It provides a graphical interface for user authentication, examinee registration, record browsing, and dashboard reporting backed by a MySQL database.

> **Project status:** This repository is an academic/course project and is not intended to replace a production electronic health-record system.

## Features

- User login and sign-up interfaces
- Add, view, and update examinee records
- Dashboard summaries for:
  - Total registered examinees
  - Male and female examinee counts
  - Student and employee counts
- Ring-chart visualizations powered by JFreeChart
- Storage of examinee demographics, contact details, medical conditions, and immunization history
- Optional Java utility for generating sample examinee data
- MySQL schema included in the repository

## Technology Stack

- **Language:** Java
- **UI:** Java Swing
- **Database:** MySQL 8.x
- **Database connectivity:** MySQL Connector/J
- **Charts:** JFreeChart and JCommon
- **IDE project:** IntelliJ IDEA (`PulsePoint.iml`)

## Repository Layout

```text
PulsePoint/
├── src/                              # Java application source
├── src/driver/                       # Runtime library JARs
├── src/icons/                        # Application icons and logos
├── src/images/                       # Images used by the application
├── PulsePoint App/preparation/       # SQL schema and data-generation utility
├── resources/                        # Additional bundled resources and drivers
└── PulsePoint.iml                    # IntelliJ IDEA project file
```

## Prerequisites

Before running PulsePoint, install or have access to:

- Java Development Kit (JDK) compatible with the source code
- MySQL Server 8.x
- IntelliJ IDEA or another Java IDE
- A MySQL account with permission to create and modify the `pulsepoint` database

## Database Setup

1. Start MySQL Server.
2. Open [`PulsePoint App/preparation/PulsePoint Structure.sql`](PulsePoint%20App/preparation/PulsePoint%20Structure.sql).
3. Run the script in MySQL Workbench or with the MySQL command-line client. The script creates the `pulsepoint` database and its tables.
4. Review the database settings in `src/PulsePointConstants.java` and update the JDBC URL, username, and password for your local environment.
5. Do not commit real database credentials. Prefer environment variables or a local, ignored configuration file for development.

## Running the Application

### IntelliJ IDEA

1. Clone the repository:

   ```bash
   git clone https://github.com/TheMoldyMustard/PulsePoint.git
   cd PulsePoint
   ```

2. Open the project in IntelliJ IDEA using `PulsePoint.iml`.
3. Ensure the MySQL Connector/J, JFreeChart, and JCommon JARs are available on the project classpath. Bundled copies are located under `src/driver/` and `resources/drivers/`.
4. Configure the database connection as described above.
5. Run the application's main window class, `MainWindow`, or launch the UI class you want to test, such as `UserLoginUI` or `Dashboard`.

## Sample Data Generator

`src/Prototyping.java` contains a utility that generates sample examinee information and inserts it into MySQL. Use it only with a development database because it creates synthetic records and writes directly to the configured database.

## Data and Privacy

The application models sensitive health-related information, including medical conditions and immunization history. Do not use real personal or medical data in development or testing without appropriate authorization, security controls, and legal compliance.

## Contributing

1. Create a feature branch from `master`.
2. Make focused changes and test them against a local MySQL database.
3. Keep credentials, generated data, IDE-specific secrets, and compiled artifacts out of commits.
4. Open a pull request describing the change and any database or setup requirements.

## Contributors

- [TheMoldyMustard](https://github.com/TheMoldyMustard) — project owner and contributor

See the [full contributors list](https://github.com/TheMoldyMustard/PulsePoint/graphs/contributors) for the latest contribution history.

## License

No license has been specified for this repository. All rights are reserved unless the project owner adds a license.
