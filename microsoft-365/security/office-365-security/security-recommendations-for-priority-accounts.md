---
title: Microsoft 365 の優先度アカウントのセキュリティに関する推奨事項
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ設定を昇格し、Microsoft 365 組織の優先度アカウントに関するレポート、アラート、調査を使用する方法について説明します。
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769247"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 の優先度アカウントのセキュリティに関する推奨事項

組織の役員から、何かの操作を求める緊急のメッセージを受け取った場合、どうしますか。 実行しますか? ほとんどのユーザーは要求に準拠します。

攻撃者の場合、ランダムなネットをキャストしてランダムまたは不明なユーザーの資格情報を取得する通常のフィッシング攻撃は非効率的です。 一方、権限または権限 _の_ 位置にあるユーザーを対象とするスピア フィッシング攻撃やむち打ち攻撃は、攻撃者に対する報酬がはるかに高い。 これらの優先度アカウントが侵害された場合、攻撃者は組織内の管理者、財務、製品、または物理的なアクセス機能を持つアカウントにアクセスする可能性があります。

Microsoft 365 と microsoft Defender for Office 365 には、優先度アカウントに追加のセキュリティ レイヤーを提供するのに役立つさまざまな機能が含まれている。 利用可能な機能とそれらを使用する方法については、この記事で説明します。

![アイコン フォームのセキュリティに関する推奨事項の概要](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a>優先度アカウントのサインイン セキュリティを強化する

優先度アカウントでは、サインインのセキュリティを強化する必要があります。 多要素認証 (MFA) を要求し、レガシ認証プロトコルを無効にすることで、サインインのセキュリティを強化できます。

手順については、手順 [1 を参照してください。MFA を使用してリモート ワーカーのサインイン セキュリティを強化します](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。 この記事ではリモート ワーカーについて説明しますが、優先度の高いユーザーに対して同じ概念が適用されます。

**注**:

- 基本認証は、Exchange Online for Exchange Web サービス (EWS)、Exchange ActiveSync、POP3、IMAP4、リモート PowerShell で廃止中です。 詳細については、このブログの投稿 [を参照してください](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

- Exchange Online の認証 [ポリシー](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) と [クライアント](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) アクセス規則を使用して、POP3、IMAP4、認証済み SMTP のような基本認証および従来の認証プロトコルをブロックできます。

- 個々のメールボックスで POP3 および IMAP4 アクセスを無効にできます。 認証済み SMTP は組織レベルで無効にし、必要な特定のメールボックスで有効にできます。 手順については、以下のトピックを参照してください。
  - [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [認証済みクライアント SMTP 送信 (SMTP AUTH) を有効または無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>優先度アカウントに厳密に設定されたセキュリティ ポリシーを使用する

優先度ユーザーには、Exchange Online Protection (EOP) と Defender for Office 365 で利用できるさまざまな保護に対して、より厳しいアクションが必要です。

たとえば、スパムとして分類されたメッセージを迷惑メール フォルダーに配信する代わりに、それらのメッセージが優先度アカウントを対象としている場合は、それらのメッセージを検疫する必要があります。

既定のセキュリティ ポリシーで Strict プロファイルを使用すると、優先度アカウントに対してこの厳格なアプローチを実装できます。

事前設定されたセキュリティ ポリシーは、EOP および Defender for Office 365 のすべての保護に推奨される Strict ポリシー設定を適用する便利な場所です。 詳細については、「EOP と Microsoft Defender for [Office 365 」](preset-security-policies.md)を参照してください。

Strict ポリシー設定と既定のポリシー設定および標準ポリシー設定との違いの詳細については、「EOP および Microsoft Defender for [Office 365](recommended-settings-for-eop-and-office365-atp.md)セキュリティの推奨設定」を参照してください。

## <a name="apply-user-tags-to-priority-accounts"></a>ユーザー タグを優先度アカウントに適用する

Office 365 プラン 2 (Microsoft 365 E5 またはアドオン サブスクリプションの一部として) 用の Microsoft Defender のユーザー タグは、レポートやインシデント調査で特定のユーザーまたはユーザー グループをすばやく識別して分類する方法です。

**優先度アカウント** は、組み込みのユーザー タグ (システム _タグと呼_ ばれる) の一種で、優先度アカウントに関連するインシデントとアラートを識別するために使用できます。 優先度アカウントの詳細については、「優先度アカウント **の** 管理と [監視」を参照してください](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

カスタム タグを作成して、優先度アカウントをさらに識別して分類することもできます。 詳細については、「ユーザー タグ [」を参照してください](user-tags.md)。 優先度アカウント (システム タグ) は **、** カスタム ユーザー タグと同じインターフェイスで管理できます。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>アラート、レポート、検出の優先度アカウントを監視する

優先度ユーザーをセキュリティで保護してタグ付けした後、EOP と Defender for Office 365 で利用可能なレポート、アラート、調査を使用して、優先度アカウントに関連するインシデントや検出をすばやく特定できます。 次の表で、ユーザー タグをサポートする機能について説明します。

<br>

****

|機能|説明|
|---|---|
|アラート|影響を受けるユーザーのユーザー タグは、セキュリティ/コンプライアンスセンターの [アラートの表示] ページにフィルター&表示されます。 詳細については、「通知の表示 [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)。|
|脅威エクスプローラー <p> リアルタイムの検出|脅威 **エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム検出 **(Microsoft** Defender for Office 365 プラン 1) では、ユーザー タグがメール グリッド ビューと [メールの詳細] フライアウトに表示されます。 ユーザー タグは、フィルター可能なプロパティとして使用することもできます。 詳細については、「脅威エクスプローラーの  [タグ」を参照してください](threat-explorer.md#tags-in-threat-explorer)。|
|キャンペーン ビュー|ユーザー タグは、Microsoft Defender 365 プラン 2 のキャンペーン ビューでフィルター処理Officeプロパティの 1 つになります。 詳細については、「キャンペーン ビュー [」を参照してください](campaigns.md)。|
|脅威保護の状態レポート|脅威保護状態レポートの事実上すべてのビューと詳細テーブルでは、優先度アカウントで結果を **フィルター処理できます**。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。|
|優先度アカウント レポートのメールの問題|Exchange **管理センター** (EAC) の優先度アカウント レポートの電子メールの問題には、優先度アカウントの配信不能メッセージと遅延メッセージに関する情報が **含まれます**。 詳細については、「優先度アカウントの [メールの問題」レポートを参照してください](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="see-also"></a>関連項目

[Microsoft Defender での優先度アカウント保護の発表 (Office 365)](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
