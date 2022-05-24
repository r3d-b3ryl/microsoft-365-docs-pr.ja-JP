---
title: Microsoft 365の優先度アカウント、優先度アカウント、Office 365の優先度アカウント、Microsoft 365の優先度アカウントに関するセキュリティに関する推奨事項
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
ms.custom: ''
description: 管理者は、セキュリティ設定を昇格させ、Microsoft 365組織の優先度アカウントのレポート、アラート、調査を使用する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 50d51bf2861d1ef1b9e4d9694fc9469fc5ec7406
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648637"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 の優先アカウントのセキュリティに関する推奨事項

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

すべてのユーザー アカウントが同じ会社情報にアクセスできるわけではありません。 一部のアカウントでは、財務データ、製品開発情報、重要なビルド システムへのパートナー アクセスなど、機密情報にアクセスできます。 侵害された場合、機密性の高い情報にアクセスできるアカウントは重大な脅威になります。 このような種類のアカウント _の優先度アカウントを_ 呼び出します。 優先度アカウントには、CEO、CISO、CFO、インフラストラクチャ管理者アカウント、ビルド システム アカウントなどが含まれます (ただし、これらに限定されません)。

攻撃者の場合、通常または未知のユーザーにランダムなネットをキャストする通常のフィッシング攻撃は非効率的です。 一方、優先度の高いアカウントを対象とする _スピア フィッシング_ 攻撃や _ホアリング_ 攻撃は、攻撃者にとって非常に報われます。 そのため、優先度の高いアカウントでは、アカウントの侵害を防ぐために、通常よりも強力な保護が必要です。

Microsoft 365とMicrosoft Defender for Office 365には、優先度アカウントのセキュリティの追加レイヤーを提供するいくつかの重要な機能が含まれています。 この記事では、これらの機能とその使用方法について説明します。

:::image type="content" source="../../media/security-recommendations-for-priority-users.png" alt-text="アイコン 形式のセキュリティに関する推奨事項の概要" lightbox="../../media/security-recommendations-for-priority-users.png":::

|タスク|すべてのOffice 365 Enterpriseプラン|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[優先度アカウントのサインイン セキュリティを強化する](#increase-sign-in-security-for-priority-accounts)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[優先度アカウントに Strict 事前設定セキュリティ ポリシーを使用する](#use-strict-preset-security-policies-for-priority-accounts)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[優先度アカウントにユーザー タグを適用する](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[アラート、レポート、検出の優先度アカウントを監視する](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[ユーザーのトレーニング](#train-users)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

> [!NOTE]
> _特権アカウント_ (管理者アカウント) のセキュリティ保護については、[このトピック](/azure/architecture/framework/security/critical-impact-accounts)を参照してください。

## <a name="increase-sign-in-security-for-priority-accounts"></a>優先度アカウントのサインイン セキュリティを強化する

優先度の高いアカウントでは、サインイン セキュリティを強化する必要があります。 多要素認証 (MFA) を要求し、レガシ認証プロトコルを無効にすることで、サインイン セキュリティを強化できます。

手順については、 [手順 1. を参照してください。MFA を使用してリモート ワーカーのサインイン セキュリティを強化します](../../solutions/empower-people-to-work-remotely-secure-sign-in.md)。 この記事ではリモート ワーカーについて説明していますが、優先度の高いユーザーにも同じ概念が適用されます。

**注**: 前の記事で説明したように、すべての優先度の高いユーザーに対してレガシ認証プロトコルをグローバルに無効にすることを強くお勧めします。 ビジネス要件でこれを防ぐ場合、Exchange Onlineはレガシ認証プロトコルの範囲を制限するのに役立つ次の制御を提供します。

- Exchange Onlineで[認証ポリシー](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)と[クライアント アクセス 規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)を使用して、特定のユーザーに対して基本的な認証と従来の認証プロトコル (POP3、IMAP4、認証済み SMTP など) をブロックまたは許可できます。

- 個々のメールボックスで POP3 および IMAP4 アクセスを無効にすることができます。 組織レベルで認証された SMTP を無効にし、引き続き必要な特定のメールボックスで有効にすることができます。 手順については、次の記事を参照してください。
  - [ユーザーの POP3 または IMAP4 アクセスを有効または無効にする](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [認証されたクライアント SMTP 送信を有効または無効にする (SMTP AUTH)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

また、基本認証は、Exchange Web サービス (EWS)、Exchange ActiveSync、POP3、IMAP4、リモート PowerShell のExchange Onlineで非推奨になっていることにも注目してください。 詳細については、この [ブログ投稿](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)を参照してください。

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>優先度アカウントに Strict 事前設定セキュリティ ポリシーを使用する

優先度の高いユーザーは、Exchange Online Protection (EOP) とDefender for Office 365で使用できるさまざまな保護に対して、より厳しいアクションを必要とします。

たとえば、迷惑メール フォルダーにスパムとして分類されたメッセージを配信する代わりに、優先度の高いアカウントを対象とする場合は、同じメッセージを検疫する必要があります。

事前設定されたセキュリティ ポリシーで Strict プロファイルを使用して、優先度アカウントに対してこの厳格なアプローチを実装できます。

事前設定されたセキュリティ ポリシーは、EOP とDefender for Office 365のすべての保護に対して推奨される厳格なポリシー設定を適用するのに便利で中央の場所です。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

厳密なポリシー設定と既定のポリシー設定と標準ポリシー設定の違いについては、「[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定](recommended-settings-for-eop-and-office365.md)」を参照してください。

## <a name="apply-user-tags-to-priority-accounts"></a>優先度アカウントにユーザー タグを適用する

Microsoft Defender for Office 365 プラン 2 のユーザー タグ (Microsoft 365 E5またはアドオン サブスクリプションの一部として) は、レポートやインシデント調査で特定のユーザーまたはユーザー グループをすばやく識別して分類する方法です。

**優先度アカウント** は、優先度アカウントを含むインシデントやアラートを識別するために使用できる組み込みのユーザー _タグ (システム タグ_ と呼ばれます) の一種です。 優先度アカウントの詳細については、「**優先度アカウントの**[管理と監視](../../admin/setup/priority-accounts.md)」を参照してください。

また、カスタム タグを作成して、優先度アカウントをさらに識別して分類することもできます。 詳細については、「 [ユーザー タグ」を](user-tags.md)参照してください。 **優先度アカウント** (システム タグ) は、カスタム ユーザー タグと同じインターフェイスで管理できます。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>アラート、レポート、検出の優先度アカウントを監視する

優先度の高いユーザーをセキュリティで保護してタグ付けした後、EOP とDefender for Office 365で使用可能なレポート、アラート、および調査を使用して、優先度の高いアカウントを含むインシデントまたは検出をすばやく識別できます。 ユーザー タグをサポートする機能を次の表に示します。

|機能|説明|
|---|---|
|アラート|影響を受けるユーザーのユーザー タグは、Microsoft 365 Defender ポータルの **[アラート**] ページでフィルターとして表示され、使用できます。 詳細については、「アラートの [表示」を参照してください](../../compliance/alert-policies.md#viewing-alerts)。|
|エクスプローラー <p> リアルタイムの検出|**エクスプローラー** (Defender for Office 365 プラン 2) または **リアルタイム検出** (Defender for Office 365 プラン 1) では、ユーザー タグが電子メール グリッド ビューと電子メールの詳細ポップアップに表示されます。 ユーザー タグは、フィルター可能なプロパティとしても使用できます。 詳細については、「  [エクスプローラーのタグ](threat-explorer.md#tags-in-threat-explorer)」を参照してください。|
|キャンペーン ビュー|ユーザー タグは、Microsoft Defender for Office 365 プラン 2 のキャンペーン ビューのフィルター可能なプロパティの 1 つです。 詳細については、「 [キャンペーン ビュー](campaigns.md)」を参照してください。|
|脅威保護の状態レポート|**脅威の保護状態レポート** のほぼすべてのビューと詳細テーブルで、**優先度アカウント** で結果をフィルター処理できます。 詳細については、 [脅威保護の状態レポートに関するページを](view-email-security-reports.md#threat-protection-status-report)参照してください。|
|優先度アカウントレポートの電子メールの問題|Exchange管理センター (EAC) の **[優先度アカウントの電子メールの問題**] レポートには、**優先度アカウント** の配信不能メッセージと遅延メッセージに関する情報が含まれています。 詳細については、「 [優先度アカウントの電子メールの問題レポート](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)」を参照してください。|

## <a name="train-users"></a>ユーザーのトレーニング

優先度の高いアカウントを使用してユーザーをトレーニングすると、それらのユーザーとセキュリティ運用チームの時間と不満を大幅に削減できます。 精通しているユーザーは、疑わしいメール メッセージで添付ファイルを開いたり、リンクをクリックしたりする可能性が低く、疑わしい Web サイトを回避する可能性が高くなります。

「中立大学ケネディ学校 [サイバーセキュリティ キャンペーン の手引き」](https://www.belfercenter.org/CyberPlaybook) には、フィッシング攻撃を特定するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスが用意されています。

Microsoft 365には、組織内のユーザーに通知するのに役立つ次のリソースが用意されています。

|概念|リソース|説明|
|---|---|---|
|Microsoft 365|[カスタマイズ可能な学習経路](/office365/customlearning/)|これらのリソースは、組織内のユーザーのトレーニングをまとめるのに役立ちます。|
|Microsoft 365 セキュリティ|[ラーニング モジュール: 組み込みのインテリジェントなセキュリティで組織をセキュリティで保護Microsoft 365](/learn/modules/security-with-microsoft-365)|このモジュールを使用すると、Microsoft 365セキュリティ機能の連携方法を説明し、これらのセキュリティ機能の利点を明確にできます。|
|多要素認証|[2 段階認証: 追加の確認ページは何ですか?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|この記事は、エンド ユーザーが多要素認証とは何か、組織で使用されている理由を理解するのに役立ちます。|
|攻撃シミュレーション トレーニング|[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)|Microsoft Defender for Office 365計画 2 の攻撃シミュレーション トレーニングを使用すると、管理者は、特定のユーザー グループに対してシミュレートされたフィッシング攻撃を構成、起動、追跡できます。|

さらに、Microsoft では、ユーザーが「 [ハッカーやマルウェアからアカウントとデバイスを保護](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)する」に記載されているアクションを実行することをお勧めします。 それらの操作を次に示します。

- 強力なパスワードを使用する
- デバイスの保護
- Windows PC と Mac PC でセキュリティ機能を有効にする (アンマネージド デバイスの場合)

## <a name="see-also"></a>関連項目

[Microsoft Defender for Office 365での優先度アカウント保護の発表](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
