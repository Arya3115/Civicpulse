# 🏙️ CivicPulse — AI-Powered Citizen Grievance Redressal System

> **Empowering citizens, streamlining governance.**
> A next-generation civic engagement platform that uses AI to automatically categorize, prioritizing, and route citizen complaints to the right department.

---

## 🌟 Features

### 🚀 For Citizens
*   **Smart Reporting**: Submit complaints with photos and location. Our AI automatically detects the category (e.g., Pothole, Garbage) and urgency.
*   **Real-time Tracking**: Track the status of your complaints (Submitted -> In Progress -> Resolved) with a transparent timeline.
*   **Gamification**: Earn XP and badges (e.g., "Civic Hero", "Guardian") for reporting valid issues.
*   **Interactive UI**: Experience a fluid, 3D interactive background and modern glassmorphism design.
*   **AI Voice Calling**: Talk directly to our AI agent (ElevenLabs Convai) on the website to report issues hands-free.
*   **Email Integration**: Report issues simply by sending an email to our bot address.
*   **Telegram Bot**: Chat with our AI assistant on Telegram to report issues or check status.

### 🛡️ For Administrators
*   **AI Triage**: Automatically prioritizes critical issues (e.g., "Open manhole") over low-priority ones.
*   **Smart Routing**: Directs complaints to the specific department (e.g., "Health", "Roads", "Electrical").
*   **Dashboard**: Visualize city-wide data with heatmaps, charts, and trend analysis.
*   **Auto-Escalation**: Complaints not resolved within the SLA are automatically escalated to higher officials.

---

## 🛠️ Tech Stack

*   **Frontend**: Next.js 16, React 19, Tailwind CSS 4, Framer Motion
*   **Backend**: Next.js API Routes (Serverless)
*   **Database**: Supabase (PostgreSQL)
*   **AI/ML**: Groq-powered AI classification and sentiment analysis; Gemini is used by the optional Telegram bot
*   **Authentication**: Supabase Auth
*   **Deployment**: Vercel

---

## 🚀 Getting Started

### Prerequisites
*   Node.js 20.9+ (recommended: current Node.js LTS)
*   npm or yarn
*   Supabase Account
*   Groq API account (for the web app AI features)
*   Google Cloud account only if you plan to run the optional Telegram bot AI features
### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/civic-pulse.git
    cd civic-pulse
    ```

2.  **Install dependencies**
    ```bash
    npm install
    cp .env.example .env.local
    ```

3.  **Environment Setup**
    Copy `.env.example` to `.env.local` in the project root, then replace the placeholders with your own values:
    ```env
    # Required for the main web app
    NEXT_PUBLIC_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
    NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_publishable_or_anon_key
    GROQ_API_KEY=your_groq_api_key

    # Optional: Google Street View feature
    NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=your_google_maps_api_key

    # Optional: email notifications
    EMAIL_USER=your_email@example.com
    EMAIL_PASS=your_email_app_password
    NEXT_PUBLIC_APP_URL=http://localhost:3000

    # Optional: Telegram bot and its AI features
    BOT_TOKEN=your_telegram_bot_token
    SUPABASE_URL=https://YOUR_PROJECT.supabase.co
    SUPABASE_KEY=your_supabase_publishable_or_anon_key
    GEMINI_API_KEY=your_gemini_api_key
    ```

4.  **Database Setup**
    Run `supabase-schema.sql` and `supabase-gamification.sql` in the Supabase SQL Editor. Create a public Storage bucket named `complaint-photos` if you want photo uploads. Review and configure Row Level Security (RLS) before using real or public data; the base schema disables RLS on some tables for demo use.

5.  **Run Locally**
    ```bash
    npm run dev
    ```
    Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🌍 Deployment

The easiest way to deploy is using **Vercel**:

1.  Push your code to GitHub.
2.  Import the project into Vercel.
3.  Add the environment variables (from step 3 above) in the Vercel Project Settings.
4.  Click **Deploy**.

For detailed instructions, see [DEPLOYMENT.md](./DEPLOYMENT.md). Copy `.env.example` to `.env.local` and replace placeholders with your own credentials. Never commit `.env.local` or real API keys.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1.  Fork the project
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Built with ❤️ for the Hackathon.
