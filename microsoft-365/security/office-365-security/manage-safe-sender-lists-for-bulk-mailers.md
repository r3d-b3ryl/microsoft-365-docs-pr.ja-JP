---
title: バルク メール業者の差出人セーフ リストを管理する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: '差出人セーフ リストを使用する場合は、Exchange Online Protection (EOP) と Outlook で処理が異なることを認識しておく必要があります。サービスでは RFC 5321.MailFrom アドレスと RFC 5322.From アドレスを検査することによって信頼できる差出人とドメインを尊重するのに対して、Outlook では RFC 5322.From アドレスをユーザーの差出人セーフ リストに追加します (注 : サービスは、ブロックする差出人とドメインについては、5321.MailFrom アドレスと 5322.From アドレスの両方を検査します)。'
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598944"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>バルク メーラーの差出人セーフ リストを管理する

差出人セーフリストを使用する場合は、Exchange Online Protection (EOP) と Outlook が異なる方法で処理することに注意してください。 Office 365 サービスは、 `RFC 5321.MailFrom`アドレスと`RFC 5322.From`アドレスを調べて、安全な送信者とドメインを尊重します`RFC 5322.From`が、Outlook はユーザーの差出人セーフリストにアドレスを追加します。 (注: サービスは、ブロックさ`5321.MailFrom`れた`5322.From`送信者とドメインのアドレスとアドレスの両方を調べます。)

と`SMTP MAIL FROM` `RFC 5321.MailFrom address`いうアドレスは、SPF チェックの実行に使用される電子メールアドレス、およびメールを配信できない場合は、バウンスメッセージが配信されるパスのことです。 この電子メールアドレスは、 `Return-Path`既定でメッセージヘッダーに配置されていますが、送信者は別`Return-Path`のアドレスを指定することもできます。

メッセージ`From:`ヘッダー内のアドレス ( `RFC 5322.From`アドレスとも呼ばれます) は、Outlook などのメールクライアントに表示される電子メールアドレスです。

多くの時間、 `5321.MailFrom`および`5322.From`アドレスは同じです。 このことは、人間同士のコミュニケーションではよく見られることです。 ただし、他のユーザーに代わって電子メールが送信される場合は、これらのアドレスが異なるのが普通です。 大部分のバルク メール メッセージでは、ほとんどの場合にそのようになります。

たとえば、青色の Yonder 航空が、青木社長の旅行を採用して、電子メール広告を送信しているとします。 受信トレイに入るメッセージの差出人は blueyonder@news.blueyonderairlines.com です。 この例では次のようになっています。

- `5321.MailFrom`アドレスは blueyonder.airlines@margiestravel.com です。

- `5322.From`アドレスは blueyonder@news.blueyonderairlines.com で、Outlook に表示されます。

このメッセージがフィルター処理されないようにするには、次のことを行います。

- [**ユーザーとして**] `RFC 5322.From` : アドレスを Outlook の信頼できる差出人として追加します。

- **管理者として**:[メールフロールール](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)(トランスポートルールとも呼ばれます) を設定します。
