[简体中文](README.md) | English

CDN acceleration and security protection for this project are sponsored by Tencent EdgeOne: EdgeOne offers a long-term free plan with unlimited traffic and requests, covering Mainland China nodes, with no overage charges. Interested friends can click the link below to claim it：[Best Asian CDN, Edge, and Secure Solutions - Tencent EdgeOne](https://edgeone.ai/zh?from=github)
![EdgeOne Logo](https://edgeone.ai/media/34fe3a45-492d-4ea4-ae5d-ea1087ca7b4b.png)
# 🛡️ Revelation's WAF Block Page

A multi-language, multi-type cybersecurity firewall block page.

![Example](https://github.com/user-attachments/assets/5bee7eb5-2566-418e-b0aa-2d83271ba25d)

# 🗂️ File Categories

| File Name | Block Type |
| :--: | :--: |
| 403 Forbidden.html | General block page for 403 requests |
| Regional Access Restriction.html | Regional access restriction |
| Non-existent Website.html | Website does not exist |
| IP Blacklist.html | IP blacklist |

The file order is consistent with the screenshot above.

# 📋 Page Main Features

## 🛜 Automatic IP Retrieval
Fetches the visitor's network IP address using `https://ipapi.co/json/` (primary API) or `https://ipinfo.io/json/` (fallback API) and displays it on the page. This IP is then used to determine other content.

## 💬 Automatic Language Switching
Detects the appropriate WAF block language for the visitor based on their IP address. Currently supports Simplified Chinese, Traditional Chinese, English, Japanese, Korean, Dutch, Portuguese, Ukrainian, Hindi, Thai, Tagalog, Vietnamese, Norwegian, Turkish, Malay, French, German, Spanish, Bulgarian, Irish, Lithuanian, Indonesian, with language mappings configured for specific countries. Once the visitor's country is identified via their IP, the page automatically displays the corresponding language based on the configured country-language mapping. If no mapping exists, the default language (English) is shown. Visitors can also manually switch languages using the icon in the upper right corner.

## ⏲ Block Time Display
Automatically determines the visitor's timezone based on their IP address. Typically displays the user's local time using UTC+offset. If the `https://ipapi.co/json/` API is rate-limited due to excessive requests, it will switch to displaying the user's local time + timezone name. If both APIs fail, the default UTC+0800 (Asia/Shanghai) time is displayed.

## 🎇 Others
Includes features like page refresh and a help pop-up window.

# 🗣 Instructions
To use, simply paste the single page into the corresponding settings area. Taking 1Panel as an example:
![1Panel Pro](https://github.com/user-attachments/assets/eaabe285-a868-4c68-b1a7-36d1f1f81079)

## 📩 Content Modification
When modifying the block page, please note:
1.  The language within the HTML body is the initial language displayed when the page is first accessed. If you want the page to display in English before fetching the IP, change it to English.
2.  To add or remove a section and its language, you need to define a new ID for that section and add this ID to the language resource pack. The same applies for deletion.
3.  To add or remove a language, you need to:
      > 1.  Add or remove the language from the language selector, ensuring the language's `data-lang` parameter is unique.
      > 2.  Add a new language resource JSON file, ensuring the class name at the beginning matches the language's `data-lang` parameter.
      > 3.  Add a mapping from the country code to the language (country codes cannot be customized, language codes can be customized).
