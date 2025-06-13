# LMS Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A modern Learning Management System built with Next.js 13 and React. It helps creators sell courses with Stripe, stream videos through Mux, and manage content effortlessly. Students gain a personalized dashboard to track progress while instructors enjoy drag-and-drop editing and insightful analytics.

## Table of Contents

- [Features](#features)
- [Demo](#demo)
- [Setup](#setup)
  - [Simple Mode Setup](#simple-mode-setup)
  - [Advanced Mode Setup](#advanced-mode-setup)
- [Usage](#usage)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [FAQ](#faq)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

## Features

- Browse and filter courses
- Purchase content securely via Stripe
- Mark chapters complete and track progress
- Teacher dashboard with course and chapter management
- Drag-and-drop reordering for chapters
- Upload thumbnails, files and videos using UploadThing
- Stream videos with Mux HLS player
- Authentication with Clerk
- Prisma ORM with MySQL/PlanetScale
- Analytics for revenue and sales

## Demo

[YouTube Tutorial](https://www.youtube.com/watch?v=Big_aFLmekI)

## Setup

Below are quick-start instructions for both beginner and advanced users. Environment variables are required in either mode.

### Simple Mode Setup

1. **Clone the Repository**
   ```bash
   git clone <repo-url>
   cd <project-name>
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment**
   ```bash
   cp .env.example .env.local
   ```
   Required variables:
   * `APP_MODE=simple`
   * `OPENAI_API_KEY=`
   * `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=`
   * `CLERK_SECRET_KEY=`
   * `NEXT_PUBLIC_CLERK_SIGN_IN_URL=`
   * `NEXT_PUBLIC_CLERK_SIGN_UP_URL=`
   * `NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=`
   * `NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=`
   * `DATABASE_URL=`
   * `UPLOADTHING_SECRET=`
   * `UPLOADTHING_APP_ID=`
   * `MUX_TOKEN_ID=`
   * `MUX_TOKEN_SECRET=`
   * `STRIPE_API_KEY=`
   * `NEXT_PUBLIC_APP_URL=http://localhost:3000`
   * `STRIPE_WEBHOOK_SECRET=`
   * `NEXT_PUBLIC_TEACHER_ID=`

4. **Run the App**
   ```bash
   npm run dev
   ```

### Advanced Mode Setup

For production use, connect a MySQL database such as PlanetScale, configure Stripe webhooks, and supply valid Mux and UploadThing credentials. Additional plugins or infrastructure (e.g., logging, monitoring, or CI/CD) can be added as desired.

## Usage

1. Sign in using Clerk authentication.
2. Browse available courses or create new ones if you are a teacher.
3. Purchase courses through the Stripe checkout flow.
4. Watch videos and mark chapters complete to track your progress.
5. Teachers can upload videos, reorder chapters, and view sales analytics.

## Deployment

This project works well with Vercel.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

1. Set the environment variables on Vercel to match your `.env.local` file.
2. Push your repository to GitHub or GitLab and import it into Vercel.
3. Click **Deploy**.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests. See `CONTRIBUTING.md` if available.

## FAQ

**Q:** Can I use a different database?

**A:** Yes. Update the `DATABASE_URL` and run Prisma migrations.

**Q:** Do I need Mux and UploadThing for local testing?

**A:** You can leave these variables empty in simple mode, but video upload and streaming features will be disabled.

**Q:** How do I become a teacher?

**A:** Set your user ID as `NEXT_PUBLIC_TEACHER_ID` in the environment variables.

## License

This project is licensed under the MIT license.

## Acknowledgements

Built with [Next.js](https://nextjs.org/), [Prisma](https://prisma.io/), [Stripe](https://stripe.com/), [Mux](https://mux.com/), [UploadThing](https://uploadthing.com/), and [Tailwind CSS](https://tailwindcss.com/).

## Contact

For support, open an issue on GitHub.

