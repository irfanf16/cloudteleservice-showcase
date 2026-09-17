# CloudTeleService — Telehealth Scheduling Platform

**Telehealth · Laravel · Queue-backed**

Appointment scheduling for remote healthcare — practitioner calendars, patient booking, payments and two-way Google Calendar sync.

> **Source code is private.** This repository documents the architecture and engineering work.

## My role
Backend engineer — scheduling logic, queue architecture and third-party calendar/payment integration.

## Engineering highlights

**Queue-backed workloads.** Laravel Horizon supervises Redis queues for appointment reminders, notification fan-out and calendar synchronisation — keeping booking requests fast while slow external calls run asynchronously.

**Action-oriented domain layer.** `lorisleiva/laravel-actions` models each business operation (book, reschedule, cancel, refund) as a single invokable class usable as a controller, job or command — one code path regardless of entry point, which matters when a reschedule can arrive from the UI, an API client or a queued retry.

**Calendar integration.** Google API client for two-way sync between practitioner availability and external calendars.

**Dual auth strategy.** Passport for OAuth2 API clients, Sanctum for first-party sessions.

**Payments.** Stripe for consultation fees, deposits and refunds.

**Schema evolution.** `doctrine/dbal` for safe in-place migrations against live appointment data.


## Screenshots

<!-- ![Practitioner Calendar](docs/practitioner-calendar.png) -->
<!-- ![Booking Flow](docs/booking-flow.png) -->

_Screenshots pending — see `docs/README.md`._

## Stack

`Laravel` · `PHP` · `MySQL` · `Redis` · `Horizon` · `Passport` · `Stripe` · `Google Calendar API` · `JavaScript`
