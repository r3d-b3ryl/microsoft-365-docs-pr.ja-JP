---
title: グループ内の優先度アカウント、Microsoft 365 アカウント、優先度アカウント、Office 365 優先度アカウントに関するセキュリティMicrosoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: 管理者は、セキュリティ設定を昇格し、組織の優先度アカウントに関するレポート、アラート、および調査をMicrosoft 365できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1cf813706a5fc0180ed36943c6bc7ae54e35ae346aba3d2b0251489e05cc715b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53844108"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>優先アカウントのセキュリティMicrosoft 365

すべてのユーザー アカウントが同じ会社情報にアクセスできる場合はありません。 一部のアカウントでは、財務データ、製品開発情報、重要なビルド システムへのパートナー アクセスなど、機密情報にアクセスできます。 侵害された場合、機密性の高い情報にアクセスできるアカウントは重大な脅威を引き起します。 これらの種類のアカウントを優先度アカウント _と呼ぶ_。 優先度アカウントには、CEO、CISO、CCFO、インフラストラクチャ管理者アカウント、ビルド システム アカウントなど (ただし、これらに限定されない) があります。

攻撃者の場合、通常のユーザーまたは不明なユーザーに対してランダムなネットをキャストする通常のフィッシング攻撃は非効率的です。 一方、優先アカウント _をターゲットとする_ スピア フィッシング攻撃や捕鯨攻撃は、攻撃者にとって非常に有益です。 そのため、優先度の高いアカウントは、アカウントの侵害を防ぐために、通常の保護よりも強力である必要があります。

Microsoft 365 Microsoft Defender for Office 365には、優先度アカウントに追加のセキュリティ層を提供するいくつかの主要な機能が含まれている必要があります。 この記事では、これらの機能とそれらを使用する方法について説明します。

![アイコン フォームのセキュリティ推奨事項の概要](../../media/security-recommendations-for-priority-users.png)

<br>

****

|タスク|すべてのOffice 365 Enterpriseプラン|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[優先アカウントのサインイン セキュリティを強化する](#increase-sign-in-security-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[優先度アカウントに厳密な事前設定されたセキュリティ ポリシーを使用する](#use-strict-preset-security-policies-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[ユーザー タグを優先度アカウントに適用する](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[アラート、レポート、検出の優先度アカウントを監視する](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[ユーザーのトレーニング](#train-users)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

> [!NOTE]
> 特権アカウント (管理者アカウント) _のセキュリティ保護の詳細については_ 、このトピックを [参照してください](/azure/architecture/framework/security/critical-impact-accounts)。

## <a name="increase-sign-in-security-for-priority-accounts"></a>優先アカウントのサインイン セキュリティを強化する

優先度の高いアカウントでは、サインイン のセキュリティが強化されている必要があります。 多要素認証 (MFA) を要求し、従来の認証プロトコルを無効にすることで、サインイン のセキュリティを強化できます。

手順については、「手順 [1」を参照してください。MFA を使用してリモート ワーカーのサインイン セキュリティを強化します](../../solutions/empower-people-to-work-remotely-secure-sign-in.md)。 この記事ではリモート ワーカーについて説明しますが、優先度の高いユーザーに対して同じ概念が適用されます。

**注**: 前の記事で説明したように、すべての優先度ユーザーに対してレガシ認証プロトコルをグローバルに無効にすることを強く推奨します。 ビジネス要件で許可されていない場合、Exchange Onlineは、従来の認証プロトコルの範囲を制限するために次のコントロールを提供します。

- Exchange Online で[](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証ポリシーとクライアント[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)アクセス ルールを使用して、特定のユーザーに対して POP3、IMAP4、認証された SMTP のような基本認証およびレガシ認証プロトコルをブロックまたは許可できます。

- 個々のメールボックスで POP3 および IMAP4 アクセスを無効にできます。 組織レベルで認証済み SMTP を無効にし、必要な特定のメールボックスで有効にできます。 手順については、次の記事を参照してください。
  - [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [認証されたクライアント SMTP 送信を有効または無効にする (SMTP AUTH)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

基本認証は、Exchange Exchange Online Web サービス (EWS)、Exchange ActiveSync、POP3、IMAP4、リモート PowerShell の Exchange Online で廃止される過程にある点にも注意してください。 詳細については、このブログ投稿 [を参照してください](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>優先度アカウントに厳密な事前設定されたセキュリティ ポリシーを使用する

優先度の高いユーザーは、Exchange Online Protection (EOP) および Defender で使用できるさまざまな保護に対して、より厳しいOffice 365。

たとえば、スパムとして分類されたメッセージを迷惑メール フォルダーに配信する代わりに、優先度の高いアカウントを対象にしている場合は、同じメッセージを検疫する必要があります。

優先度アカウントに対してこの厳格なアプローチを実装するには、事前設定されたセキュリティ ポリシーの Strict プロファイルを使用します。

事前設定されたセキュリティ ポリシーは、EOP および Defender for Office 365 のすべての保護に対して推奨される厳密なポリシー設定を適用する便利で中心的な場所です。 詳細については、「EOP でのセキュリティ ポリシーの事前設定」および[「Microsoft Defender for microsoft Defender for Office 365」 を参照してください](preset-security-policies.md)。

厳密なポリシー設定が既定のポリシー設定と標準ポリシー設定とどのように異なるかについては、「EOP および Microsoft Defender のセキュリティに関する推奨設定」[をOffice 365してください](recommended-settings-for-eop-and-office365.md)。

## <a name="apply-user-tags-to-priority-accounts"></a>ユーザー タグを優先度アカウントに適用する

microsoft Defender for Office 365 Plan 2 のユーザー タグ (Microsoft 365 E5 またはアドオン サブスクリプションの一部として) は、レポートやインシデント調査で特定のユーザーまたはユーザー グループをすばやく識別して分類する方法です。

**優先度アカウント** は、優先度アカウントに関連するインシデントやアラートを識別するために使用できる組み込みのユーザー タグ (システム _タグと呼_ ばれる) の一種です。 優先度アカウントの詳細については **、「優先度** アカウントの管理 [と監視」を参照してください](../../admin/setup/priority-accounts.md)。

カスタム タグを作成して、優先度アカウントをさらに識別して分類することもできます。 詳細については、「ユーザー タグ [」を参照してください](user-tags.md)。 優先度アカウント ( **システム タグ** ) は、カスタム ユーザー タグと同じインターフェイスで管理できます。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>アラート、レポート、検出の優先度アカウントを監視する

優先度の高いユーザーをセキュリティで保護してタグ付けした後、EOP および Defender for Office 365 で使用可能なレポート、アラート、および調査を使用して、優先度アカウントに関連するインシデントや検出をすばやく特定できます。 ユーザー タグをサポートする機能については、次の表で説明します。

<br>

****

|機能|説明|
|---|---|
|アラート|影響を受けるユーザーのユーザー タグは、ポータルの [通知] ページでフィルターとして表示Microsoft 365 Defenderできます。 詳細については、「アラートの表示 [」を参照してください](../../compliance/alert-policies.md#viewing-alerts)。|
|エクスプローラー <p> リアルタイムの検出|Explorer **(Defender** for Office 365 Plan 2) またはリアルタイム検出 **(Defender** for Office 365 Plan 1) では、ユーザー タグが [メール] グリッド ビューと [電子メールの詳細] フライアウトに表示されます。 ユーザー タグは、フィルター可能なプロパティとして使用することもできます。 詳細については、「Explorer の  [タグ」を参照してください](threat-explorer.md#tags-in-threat-explorer)。|
|キャンペーン ビュー|ユーザー タグは、Microsoft Defender のキャンペーン ビューの多くのフィルター可能なプロパティの 1 つで、Office 365 2 です。 詳細については、「キャンペーン ビュー [」を参照してください](campaigns.md)。|
|脅威保護の状態レポート|脅威保護状態レポートの事実上すべてのビューと詳細テーブルで、優先度アカウントで結果を **フィルター処理できます**。 詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。|
|優先度アカウントレポートの電子メールの問題|Exchange 管理センター (EAC) の [優先度アカウントの電子メールの問題] レポートには、優先度アカウントの配信不能メッセージと遅延メッセージに関する情報 **が含まれます**。 詳細については、「優先度アカウントの [電子メールの問題」レポートを参照してください](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|
|

## <a name="train-users"></a>ユーザーのトレーニング

優先度アカウントを使用してユーザーをトレーニングすると、それらのユーザーとセキュリティ運用チームの時間とフラストレーションを節約できます。 精通したユーザーは、疑わしい電子メール メッセージで添付ファイルを開く、またはリンクをクリックする可能性が低く、疑わしい Web サイトを避ける可能性が高い。

Harvard Kennedy School [Cybersecurity キャンペーン](https://www.belfercenter.org/CyberPlaybook) ハンドブックは、フィッシング攻撃を識別するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。

Microsoft 365、組織内のユーザーに通知するための次のリソースを提供します。

<br>

****

|概念|リソース|Description|
|---|---|---|
|Microsoft 365|[カスタマイズ可能な学習経路](/office365/customlearning/)|これらのリソースは、組織内のユーザーのトレーニングをまとめる上で役立ちます。|
|Microsoft 365 セキュリティ|[ラーニングモジュール: 組み込みのインテリジェント なセキュリティで組織をセキュリティで保護Microsoft 365](/learn/modules/security-with-microsoft-365)|このモジュールを使用すると、セキュリティ機能Microsoft 365機能を説明し、これらのセキュリティ機能の利点を明確にできます。|
|多要素認証|[2 段階認証: 追加の検証ページとは](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|この記事は、エンド ユーザーが多要素認証とは何か、および組織で使用される理由を理解するのに役立ちます。|
|攻撃シミュレーション トレーニング|[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)|Microsoft Defender for Office 365 プラン 2 の攻撃シミュレーション トレーニングを使用すると、管理者は特定のユーザー グループに対するシミュレートされたフィッシング攻撃を構成、起動、追跡できます。|

さらに、Microsoft では、この記事で説明されているアクションを実行するようにお勧めします。アカウントとデバイスをハッカーやマルウェア [から保護します](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 それらの操作を次に示します。

- 強力なパスワードの使用
- デバイスの保護
- デバイス PC および Mac pc Windows 10セキュリティ機能の有効化 (非管理対象デバイスの場合)

## <a name="see-also"></a>関連項目

[Microsoft Defender の優先度アカウント保護をユーザーに対してOffice 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
