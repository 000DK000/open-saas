# Wasp SaaS Template w/ GPT API, Google Auth, Tailwind, & Stripe Payments

<img src='src/client/static/gptsaastemplate.png' width='700px'/>

## Running it locally
After cloning this repo, you can run it locally by following these steps:

1. Install [Wasp](https://wasp-lang.dev) by running `curl -sSL https://get.wasp-lang.dev/installer.sh | sh` in your terminal.
2. Create a `.env.server` file in the root of the project
3. Copy the `env.example` file contents to `.env.server` and fill in your API keys
4. Run `wasp db migrate-dev`
5. Run `wasp start`
6. Go to `localhost:3000` in your browser (your NodeJS server will be running on port `3001`)
7. Install the Wasp extension for VSCode to get syntax highlighting on the `main.wasp` file and other features
8. Check the files for comments containing specific instructions
9. Enjoy and Have fun. When you create an App with this template, be kind and let me know by tagging me on twitter [@hot_town](https://twitter.com/hot_town)

## How it works

- 🐝 [Wasp](https://wasp-lang.dev) - allows you to build full-stack apps with 10x less boilerplate
- 🎨 [Tailwind CSS](https://tailwindcss.com/) - CSS that's easy to work with
- 🤖 [OpenAI](https://openai.com/) - GPT-3.5 turbo API
- 💸 [Stripe](https://stripe.com/) - for payments
- 📧 [SendGrid](https://sendgrid.com/) - for email

[Wasp](https://wasp-lang.dev) as the full-stack framework allows you to describe your app’s core features in the `main.wasp` config file in the root directory. Then it builds and glues these features into a React-Express-Prisma app for you so that you can focus on writing the client and server-side logic instead of configuring. For example, I did not have to use any third-party libraries for Google Authentication. I just wrote a couple lines of code in the config file stating that I want to use Google Auth, and Wasp configures it for me. Check out the comments `main.wasp` file for more.

[Stripe](https://stripe.com/) makes the payment functionality super easy. I just used their `Subscription` feature. After the user pays, their `hasPaid` and `datePaid` fields are updated in the database via the webhook found in the `src/server/serverSetup.ts` file. 

[Wasp's integrated Jobs](https://wasp-lang.dev/docs/language/features#jobs) feature is used to run a cron job every week to send an newsletter email. I used [SendGrid](https://sendgrid.com/) for the email service.

If you have any other questions, feel free to reach out to me on [twitter](https://twitter.com/hot_town)