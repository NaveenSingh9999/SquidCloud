# READ THIS FIRST — YES, BEFORE YOU COMMENT

This is the **public showcase repository** for SquidCloud. The actual production codebase is private. What you see here is the README, documentation, and release history — not the source code.

This file exists because a surprisingly large number of people prefer to type a confident wrong opinion in a comment section rather than spend 60 seconds reading the documentation. This file is for those people. Read it carefully. There is a good chance your question or criticism is already answered below, and you will look considerably less uninformed if you check before posting.

---

## What This Repository Is

A showcase. Documentation. Release history. That is all.

The production codebase is private. The product is live at [https://squidcloud.vercel.app](https://squidcloud.vercel.app). If you want to use it, go there. If you want to audit the source code, that is not available here and asking for it in the issues tab will not change that.

---

## What This Repository Is Not

- It is not the full source code
- It is not abandonware
- It is not a honeypot
- It is not AI slop
- It is not a scam
- It is not affiliated with any company that wronged you previously
- It is not obligated to meet your personal standards for what a project should look like

---

## Frequently Asked Questions from People Who Did Not Read Anything

---

**"You are abusing GitHub storage."**

No. Files uploaded to SquidCloud are split into chunks on the client side, encrypted with AES-256-GCM via the Res54 engine, serialized as JSON blobs, and stored in GitHub repositories. GitHub receives opaque, encrypted binary noise. No filename, no file type, no content, no metadata can be extracted from the stored blobs by anyone — including GitHub, including us, including you. This does not violate GitHub's Terms of Service. Read it. The relevant section does not prohibit storing encrypted data in repositories. Multiple legitimate production projects use GitHub as a storage backend. If you have a specific clause to cite, cite it. Otherwise this conversation is over.

---

**"Military-grade is a meaningless marketing term."**

You are correct that it is an overused phrase and we have moved away from it. To be precise and technical: SquidCloud uses AES-256-GCM encryption, client-side chunking before any data leaves the device, block-split architecture, optional entropy layer, and user-supplied encryption keys via BYOK. AES-256-GCM is the same standard used by governments, financial institutions, and security agencies globally. If you believe the implementation is weak, you have explicit permission to test it. Submit your findings properly. We will read them and respond seriously. Drive-by comments without technical substance will be ignored.

---

**"This looks like a honeypot."**

A honeypot is a system designed to attract and monitor attackers without their knowledge. SquidCloud is a publicly documented cloud storage platform with a release history going back to April 2025, a signed Android APK, a REST API, a CLI, an SDK, BYOS support, BYOK support, and a privacy policy. If your definition of honeypot includes all of those things, your definition needs work. If you have a specific technical concern about how data is handled, the documentation explains the architecture in full. Read it.

---

**"The source code is not public so I cannot trust it."**

That is a reasonable position and you are entitled to hold it. Closed source software exists across the entire industry including tools you use daily without question. The choice not to open source a project is not evidence of malicious intent — it is a product decision. What you should evaluate is the documented architecture, the encryption model, and whether the claims made are technically coherent. They are. If closed source is a hard requirement for you, that is fine. There are other tools. But stating "closed source equals untrustworthy" as a universal fact while using closed source software to type that comment is a position worth examining.

---

**"You are using Gmail. That is unprofessional."**

Correct. A custom domain email is coming. This has zero bearing on the encryption architecture, the storage model, the security of your files, or any technical aspect of the platform. If your threat model includes "the developer uses Gmail therefore my AES-256-GCM encrypted files are compromised," your threat model has a gap in it.

---

**"This is AI slop."**

AI tools were used in parts of the development process. So are compilers, package managers, UI frameworks, open source libraries, and documentation generators. Using tools is how software is built in 2026. The Res54 distributed storage architecture, the client-side chunking pipeline, the BYOK and BYOS systems, the encrypted GitHub storage layer, the Android build pipeline with GitHub Actions, the SquidLab SDK, and the full product were designed, built, maintained, and iterated on by one person over the course of a year. The commit history spans from March 2025 to present and is not fabricated. If you can show that AI generated the architecture decisions, the encryption design, or the system integration work, do so. Otherwise the comment reflects nothing about the project and everything about the commenter.

---

**"Your old README had terrible AI-generated marketing copy in it."**

An older public repository had outdated content that was not representative of the current product. It has been corrected and replaced with accurate technical documentation. Projects evolve. Judging the current state of a product by the worst version of its old marketing copy is not a serious critique.

---

**"Res54 sounds made up. What is it?"**

It is the name of the internal distributed storage architecture that powers SquidCloud's file handling. It is not an open standard, a third-party library, or an acronym you will find on Wikipedia. It is proprietary. Named internal systems existing in private software is normal. If the name bothers you more than the technical description of what it does, that is an interesting priority order.

---

**"Why is the version number at v11? This project looks too new for that."**

Because version numbers reflect the internal development history, not the public launch date. SquidCloud went through v9 and v10 as full development cycles while the version system was tracking sub-releases under v8. When the versioning was corrected, the number was brought in line with where the product actually was. The commit history backs this up. Version numbers are chosen by the developer, not assigned by a committee based on how old a project looks.

---

**"This is not self-hosted so it does not belong in r/selfhosted."**

Correct. Wrong community. Noted. SquidCloud supports BYOS which means you can attach your own storage infrastructure, but the platform itself is hosted. That distinction is valid and the post was in the wrong place. It will not happen again.

---

**"I do not trust a project with no public contributors."**

It is a solo project. Solo projects exist, ship, and are used by real people constantly. The absence of a contributor list does not indicate the project is fake, abandoned, or unsafe. One person building and maintaining a product is not a red flag — it is the origin story of a significant portion of the software you use today.

---

**"There is no company behind this. How do I know it will not just disappear?"**

You do not. That is an honest answer. SquidCloud is an independent project run by one person. It is not backed by venture capital or a registered company. It has been live and actively developed for over a year with no signs of stopping. The BYOS feature specifically exists so that your files can live on your own infrastructure — meaning even if SquidCloud as a platform ceased to exist, your data would still be on your own servers. That is by design.

---

**"The landing page looks AI generated."**

The landing page was built with React, TypeScript, Tailwind, and Shadcn/ui. If the quality of the design reads as AI-generated to you, that is design feedback we are happy to take seriously. If you mean the copy sounds like a language model wrote it, point to the specific line and we will evaluate it. Vague aesthetic dismissals are not actionable.

---

**"Why should I use this over Google Drive or Dropbox?"**

You probably should not if your priority is ecosystem integration, brand familiarity, or third-party app support. Google Drive and Dropbox are mature, well-funded products with enormous teams. SquidCloud does not compete on those dimensions. It competes on privacy, encryption architecture, storage flexibility, and the ability to bring your own keys and your own servers. If those things matter to you, SquidCloud is worth trying. If they do not, Google Drive is fine.

---

**"The project started as CloudBliss. What happened to that?"**

CloudBliss was the original name used during early development. The project was rebranded to SquidCloud in September 2025. Same codebase, same architecture, different name. Rebranding is normal. It does not indicate deception.

---

**"You said you take no responsibility for Supabase security. That is concerning."**

Supabase is used for authentication and metadata storage only. File content is never stored in or transmitted to Supabase. If Supabase were compromised, an attacker would see account information and file metadata — not file content. File content lives encrypted in GitHub or your own BYOS provider. The encryption architecture is designed so that a breach of any single component does not expose file content. That is the point.

---

**"How do I know my files are actually encrypted and you are not just saying that?"**

You can verify it yourself. Upload a file using native GitHub storage. Then go to the GitHub repository directly and look at what is stored. You will find JSON blobs of random-looking encrypted data with no resemblance to your original file. The filename, file type, and content are all unidentifiable. That is not a claim — it is something you can check in sixty seconds.

---

**"What happens if SquidCloud goes down?"**

If you use BYOS, nothing happens to your files. They are on your own infrastructure and you can access them directly through your provider. If you use native GitHub storage, your encrypted blobs remain in the GitHub repository and can be accessed directly. The SquidCloud interface going down does not equal your data disappearing. This is intentional.

---

**"Is this GDPR compliant?"**

SquidCloud is operated under Indian law and complies with India's Digital Personal Data Protection Act 2023. GDPR is a European regulation. If you are an EU user, the relevant data handling principles — minimal data collection, user rights to access and deletion, no selling of data — are all met by SquidCloud's architecture and Privacy Policy even if formal GDPR certification is not claimed. Read the Privacy Policy at squidcloud.vercel.app/privacy.

---

**"You store data on Vercel. Vercel can see everything."**

Vercel hosts the web platform — the frontend and serverless functions. It does not store your files. File content never passes through Vercel's storage. Vercel processes web requests and may log performance data, which is standard for any hosting provider. Your encrypted file chunks go to GitHub or your BYOS provider, not to Vercel's storage layer.

---

**"The Android APK is not on the Play Store. That is a red flag."**

Publishing on the Play Store requires a developer account fee and a review process. The signed APK is distributed directly because it is faster and does not require waiting on Google's review pipeline. Side-loading APKs is a standard practice for independent Android apps. The APK is signed — meaning it has not been tampered with since it was built. Installing from outside the Play Store is a user choice that Android explicitly supports. If you are uncomfortable with that, do not install it.

---

**"I found a bug / security issue."**

Good. Email hellosquidcloud@gmail.com with the subject line "Security Disclosure" or "Bug Report." Provide as much detail as possible. We read every message and respond to genuine reports. Please do not post security vulnerabilities publicly in issues or comments — responsible disclosure is appreciated and will be acknowledged.

---

**"Can I contribute?"**

The codebase is private so direct code contributions are not possible at this time. However, feedback, bug reports, feature requests, and testing are all genuinely welcome. Open an issue or send an email.

---

**"Is this free?"**

Yes. Completely free. No credit card. No trial period. No freemium gotcha. Free to use with no current plans to change that.

---

**"Why would anyone build this for free?"**

Because not everything needs to be a business. Some people build things because they want them to exist. SquidCloud exists because its developer wanted a storage platform that actually respected user privacy and gave users real control. It is free because that is how it should be. If that answer does not satisfy you, that is fine.

---

## A Note on Commenting

If you have a genuine technical question, a real security concern, an honest critique, or useful feedback — we want to hear it. Seriously. That kind of engagement makes the product better and is always welcome.

If you are here to post a one-line dismissal, call it AI slop without reading anything, make confident claims about things you did not research, or compare it unfavourably to enterprise software built by hundred-person teams with nine-figure budgets — save it. The project exists, people use it, and it will continue to be built regardless of what the comments section says.

One year of commits does not lie. Neither does a signed APK, a working API, and users who have been there since day one.

---

## Contact

**Email:** hellosquidcloud@gmail.com  
**Platform:** https://squidcloud.vercel.app  
**Privacy Policy:** https://squidcloud.vercel.app/privacy  
**Terms of Service:** https://squidcloud.vercel.app/terms  

We respond to real questions. We do not respond to drive-by criticism from accounts with no public projects of their own.

---

*SquidCloud — v11.1.0 Feijoa Update. Built solo. One year in. Still here. Still building. 🦑☁️*
