---
title: Broken page
deprecated: false
hidden: false
metadata:
  robots: index
---
<Embed url="https://www.youtube.com/watch?v=tak6xo-ls_s" href="https://www.youtube.com/watch?v=tak6xo-ls_s" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Ftak6xo-ls_s%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dtak6xo-ls_s%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Ftak6xo-ls_s%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

> 📘 Deeper Dive
>
> For more in-depth information, check out our detailed documentation on the following topics:
> <a href="https://docs.akeyless.io/docs/static-secrets" target="_blank">Static Secrets</a>


> 👍 Need any help?
>
> If something in this tutorial isn't working as expected, feel free to contact our support team [via Slack](https://akeylesssupport.slack.com/join/shared_invite/zt-dgjcbscx-rXlZIXsmI1sS5Yc~XrFvGw#/shared-invite/email).

***Below is a text-only guide for users based on the above video***

## What is a Static Secret?

A static secret is a key/value pair. These are usually secrets that are updated manually, such as passwords, API tokens, Personally Identifiable Information (PII), and more. Static secrets are generally updated on a less frequent basis and must be manually updated.

Secrets can be created in 3 ways:

* Akeyless Web Console
* Akeyless CLI
* Automation/Scripts

We will go through the first two for now.

## Creating a Static Secret via the UI

Choose ‘New’ → ‘Static Secret’ in the *Secrets & Keys* menu.

<Image align="center" src="https://files.readme.io/f042731-Screenshot_2024-06-02_at_13.40.11.png" />

Enter the *Name* and *Value* of the Secret. Additionally, you may optionally add a Location (or virtual folder) in which to place the Secret.

<Image align="center" src="https://files.readme.io/1f6f49a-Screenshot_2024-06-02_at_13.40.41.png" />

The new Secret will appear within that folder or in the main directory, depending on where you created the Secret.

<Image align="center" src="https://files.readme.io/509a03b-Screenshot_2024-06-02_at_13.48.23.png" />

You will see the secret within the directory it is created.

<Image align="center" src="https://files.readme.io/4d64e4d-Screenshot_2024-06-02_at_13.54.52.png" />

## Fetching a Static Secret via the UI

To fetch a static secret inside the Akeyless UI, click on the eye symbol and you will decrypt the value. You can also choose to copy the value to the clipboard.

<Image align="center" src="https://files.readme.io/8fd26e4-Screenshot_2024-06-02_at_13.41.08.png" />

## Updating and Rolling Back a Static Secret via the UI

To update a static secret value, click on the pencil icon next to the value and enter your new value. This will create a new version of the static secret. Ensure you choose the option to "Keep Previous Version".

<Image align="center" src="https://files.readme.io/cb64c80-Screenshot_2024-06-02_at_13.41.26.png" />

You will now see a new column titled "Versions" at the top. To roll back the secret to a previous version, click into that section and click on the clock icon, then *Restore*.

<Image align="center" src="https://files.readme.io/7878a0c-Screenshot_2024-06-02_at_13.42.19.png" />

Once that's done, it will create a third version that matches the version you rolled back to.

## Creating a Static Secret via the CLI

Open your terminal and ensure you have the CLI installed ([How to Install CLI](https://docs.akeyless.io/v4/docs/install-and-configure-the-akeyless-cli)).

Run the below command in your terminal, replacing \[folder\_name], \[secret\_name], and \[secret\_value]. You can use `-n` or `--name` interchangeably.

```shell
akeyless create-secret -n /[folder_name]/[secret_name] -v [secret_value]
```

The output should look like this:

<Image align="center" src="https://files.readme.io/6287a48-static9.1.jpg" />

The secret will be created in the directory you chose, as seen in the image below.

<Image align="center" src="https://files.readme.io/187c727-Screenshot_2024-06-02_at_13.43.20.png" />

## Fetching a Static Secret via the CLI

To fetch a secret, run the below command in your terminal, replacing \[folder\_name], \[secret\_name], and \[secret\_value].

```
akeyless get-secret-value -n /[folder_name]/[secret_name]
```

The output should look like this:

<Image align="center" src="https://files.readme.io/b7bbbcc-static12.png" />

## Updating and Rolling Back a Static Secret via the CLI

To update a secret, run the below command in your terminal, replacing \[folder\_name], \[secret\_name], and \[secret\_value]. Use the `--keep-prev-version=true` flag to ensure you can roll back the secret value.

```
akeyless update-secret-val -n /[folder_name]/[secret_name] -v [new-value] --keep-prev-version=true
```

The output should look like this:

<Image align="center" src="https://files.readme.io/d800ac8-static13.png" />

You can now view the updated secret by running the normal `akeyless get-secret-value` command:

<Image align="center" src="https://files.readme.io/d504f56-static14.png" />

If you want to see more information about the secret as well as previous values, you can run the following command:

```
akeyless describe-item -n /[folder_name]/[secret_name] --show-versions
```

The output should look like this:

<Image align="center" src="https://files.readme.io/3395347-Screenshot_2024-06-02_at_13.44.48.png" />

You can also see any previous version by running the following command:

```
akeyless get-secret-value -n /[folder_name]/[secret_name] --version [number]
```

The output should look like this:

<Image align="center" src="https://files.readme.io/06efb08-static17.png" />

To roll back a value, run the following command:

```
akeyless rollback-secret -n /[folder_name]/[secret_name] --old-version [number]
```

The output should look like this:

<Image align="center" src="https://files.readme.io/273131d-static19.png" />

And when you run the `akeyless get-secret-value` command again, you get the output of the secret after it was rolled back. This rollback process creates a new version of the secret that matches the value you chose to roll back to.