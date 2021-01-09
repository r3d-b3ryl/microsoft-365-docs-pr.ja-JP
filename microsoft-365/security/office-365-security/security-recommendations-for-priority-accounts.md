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
- m365solution-overview
- m365solution-protecthve
description: 管理者は、セキュリティ設定を昇格し、Microsoft 365 組織の優先度アカウントに関するレポート、アラート、調査を使用する方法について説明します。
ms.openlocfilehash: acd2eba0acd533d0cd8223f2c433cc023fc23287
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790128"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 の優先度アカウントのセキュリティに関する推奨事項

すべてのユーザー アカウントが、同じ会社情報にアクセスできるのではありません。 一部のアカウントは、財務データ、製品開発情報、重要なビルド システムへのパートナー アクセスなどの機密情報にアクセスできます。 非常に機密性の高い機密情報にアクセスできるアカウントは、侵害された場合に深刻な脅威を引き起します。 これらの種類のアカウント優先度アカウントを _呼び出します_。 優先度アカウントには、CEO、CIS、CFO、インフラストラクチャ管理者アカウント、システム アカウントの構築などがあります。

攻撃者の場合、通常のユーザーまたは不明なユーザーにランダムなネットをキャストする通常のフィッシング攻撃は非効率的です。 一方、優先度アカウント _を対象_ とするスピア フィッシング攻撃やむち打ち攻撃は、攻撃者に対して非常に高い報酬を与えるのです。 そのため、アカウントが侵害されるのを防ぐために、優先度アカウントには通常より強力な保護が必要です。

Microsoft 365 と microsoft Defender for Office 365 には、優先度アカウントの追加のセキュリティ レイヤーを提供するいくつかの主要な機能が含まれている。 この記事では、これらの機能とそれらを使用する方法について説明します。

![アイコン フォームでのセキュリティに関する推奨事項の概要](../../media/security-recommendations-for-priority-users.png)

****

|Task|すべての Office 365 Enterprise プラン|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[優先度アカウントのサインイン セキュリティを強化する](#increase-sign-in-security-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[優先度アカウントに厳密な事前設定セキュリティ ポリシーを使用する](#use-strict-preset-security-policies-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[ユーザー タグを優先度アカウントに適用する](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[アラート、レポート、検出の優先度アカウントを監視する](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>優先度アカウントのサインイン セキュリティを強化する

優先度アカウントでは、サインインのセキュリティを強化する必要があります。 多要素認証 (MFA) を要求し、レガシ認証プロトコルを無効にすることで、サインインのセキュリティを強化できます。

手順については、手順 [1 を参照してください。MFA を使用してリモート ワーカーのサインイン セキュリティを強化します](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。 この記事ではリモート ワーカーについて説明しますが、優先度の高いユーザーに対して同じ概念が適用されます。

**注**: 前の記事で説明したように、すべての優先度ユーザーに対してレガシ認証プロトコルをグローバルに無効にすることを強く推奨します。 ビジネス要件によってそれが妨げる場合、Exchange Online は、レガシ認証プロトコルの範囲を制限するために次の制御を提供します。

- Exchange Online[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)の認証ポリシー[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)とクライアント アクセス規則を使用して、POP3、IMAP4、認証済み SMTP など、基本認証と従来の認証プロトコルを特定のユーザーに対してブロックまたは許可できます。

- 個々のメールボックスで POP3 および IMAP4 アクセスを無効にできます。 認証済み SMTP は組織レベルで無効にし、必要な特定のメールボックスで有効にできます。 手順については、以下のトピックを参照してください。
  - [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [認証済みクライアント SMTP 送信 (SMTP AUTH) を有効または無効にする](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

基本認証は、Exchange Online for Exchange Web サービス (EWS)、Exchange ActiveSync、POP3、IMAP4、リモート PowerShell で廃止される過程にある点にも注意してください。 詳細については、このブログの投稿 [を参照してください](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>優先度アカウントに厳密な事前設定セキュリティ ポリシーを使用する

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

優先度ユーザーをセキュリティで保護してタグ付けした後、EOP と Defender for Office 365 で利用可能なレポート、アラート、調査を使用して、優先度アカウントに関連するインシデントや検出をすばやく特定できます。 ユーザー タグをサポートする機能を次の表に示します。

<br>

****

|機能|説明|
|---|---|
|アラート|影響を受けるユーザーのユーザー タグは、セキュリティ/コンプライアンスセンターの [アラートの表示] ページにフィルター&表示されます。 詳細については、「通知の表示 [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)。|
|脅威エクスプローラー <p> リアルタイムの検出|脅威 **エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム検出 **(Microsoft** Defender for Office 365 プラン 1) では、ユーザー タグがメール グリッド ビューと [メールの詳細] フライアウトに表示されます。 ユーザー タグは、フィルター可能なプロパティとして使用することもできます。 詳細については、「脅威エクスプローラーの  [タグ」を参照してください](threat-explorer.md#tags-in-threat-explorer)。|
|キャンペーン ビュー|ユーザー タグは、Microsoft Defender 365 プラン 2 のキャンペーン ビューでフィルター処理Officeプロパティの 1 つになります。 詳細については、「キャンペーン ビュー [」を参照してください](campaigns.md)。|
|脅威保護の状態レポート|脅威保護状態レポートの事実上すべてのビューと詳細テーブルでは、優先度アカウントで結果を **フィルター処理できます**。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。|
|優先度アカウントレポートのメールの問題|Exchange **管理センター** (EAC) の優先度アカウント レポートの電子メールの問題には、優先度アカウントの配信不能メッセージと遅延メッセージに関する情報が **含まれます**。 詳細については、「優先度アカウントの [メールの問題」レポートを参照してください](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="see-also"></a>関連項目

[Microsoft Defender での優先度アカウント保護の発表 (Office 365)](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
