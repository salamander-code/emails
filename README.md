## Responsive Email Templates

Responsive HTML email templates built with [Maizzle](https://maizzle.com).

## Getting Started

There are two ways to get started:

1. Use the compiled files
2. Use the Maizzle project

### Compiled files

The quickest way to get started is with templates from the `dist` folder.

Templates inside this folder are ready to use, so you can simply copy/paste the HTML code into your <abbr title="Email Service Provider">ESP</abbr>. Of course, you may edit the text and image paths for any of these templates, in your favorite code editor.

### Maizzle project

If you'd like to use [Maizzle](https://maizzle.com) and [Tailwind CSS](https://tailwindcss.com) to further customize the emails, you'll need to follow some extra steps.

1. First, make sure you have [Node.js](https://nodejs.org/en/download/) installed - this will also install NPM, which offers commands that we'll need, like `npm install`.

    Once you have Node.js and NPM installed, open a Terminal and run this command:

    ```sh
    npm install -g @maizzle/cli
    ```

    This installs the Maizzle CLI tool, which lets you run commands like `maizzle serve` for local development, or `maizzle build production` for building production-ready emails.

2. Next, make sure that you're inside the project directory.

    ```sh
    # `cd` into the project directory
    cd mailer-transactional
    ```

    You'll know you're in the right folder if you run the `ls` command next, and see the `package.json` file name listed in the output, among others.

3. Inside this directory, run the following command to install Maizzle's dependencies:

    ```sh
    npm install
    ```

Once it finishes, you're ready to use Maizzle to customize and build the emails.

#### Maizzle Build Commands

For local development, with live browser preview:

```sh
maizzle serve
```

For production-ready emails:

```sh
maizzle build production
```

#### NPM Scripts

You can run Maizzle build commands without installing the CLI tool.

For local development, with live browser preview:

```sh
npm run dev
```

For production-ready emails:

```sh
npm run build
```

#### Tailwind CSS

The Maizzle project comes with a custom `tailwind.config.js` that extends the original config with email-optimized utility classes that based on a design system.

##### Notable differences

There are a few differences between the original `tailwind.config.js` in Tailwind CSS and the one in Maizzle, which we've customized.

The first thing you'll notice is that the `rem` spacing scale has been replaced with a `px` scale. This is required for HTML emails, because email clients have poor support for `rem`.

###### Colors

- we have added custom color palettes like `primary` or `sunglow`
- the `gray` and `teal` palettes use custom colors

###### Spacing

- spacing scale also includes %-based utilities
- `lineHeight`, `letterSpacing`, `maxWidth`, `minHeight`, and `minWidth` have been extended to use the spacing scale (some of them do not use it by default, in Tailwind)

###### Fonts

- font families have been simplified for better email compatibility
- font size and letter spacing scales use `px`

###### Disabled plugins

The `backgroundOpacity`, `borderOpacity`, `textOpacity` core Tailwind plugins are disabled, as they generate CSS that isn't well supported in email clients.

## About Maizzle

Maizzle is an email framework that helps you quickly build HTML emails with [Tailwind CSS](https://tailwindcss.com/).

Maizzle documentation is available at https://maizzle.com
