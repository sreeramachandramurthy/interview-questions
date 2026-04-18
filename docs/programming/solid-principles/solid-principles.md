# SOLID Principles

The SOLID principles are a set of five key design principles in object-oriented programming (OOP) that help developers create software that is easier to understand, maintain, and extend. They were introduced by Robert C. Martin (Uncle Bob) and are widely used in software engineering best practices.

## S — Single Responsibility Principle (SRP)

> A class should have only one reason to change.

**Meaning**: Each class should do one thing and do it well.

Why: If a class has multiple responsibilities, changes in one area can unintentionally affect others.

Example:

❌ A Report class that both generates and prints reports.

✅ Split into ReportGenerator and ReportPrinter.