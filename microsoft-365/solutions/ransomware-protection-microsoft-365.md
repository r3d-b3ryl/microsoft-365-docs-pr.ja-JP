---
title: Microsoft 365 テナントにランサムウェア保護を展開する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
- m365solution-overview
ms.custom: seo-marvel-jun2020
keywords: ランサムウェア、人が操作するランサムウェア、人間が操作するランサムウェア、HumOR、強要攻撃、ランサムウェア攻撃、暗号化、暗号ウイルス学
description: ランサムウェア攻撃から Microsoft 365 リソースを保護する手順を説明します。
ms.openlocfilehash: e7adafd8c60e55c7bb1acc60afcd4ca5cadedb85
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444662"
---
# <a name="deploy-ransomware-protection-for-your-microsoft-365-tenant"></a>Microsoft 365 テナントにランサムウェア保護を展開する

ランサムウェアは、ファイルやフォルダーを破棄または暗号化する一種の強要攻撃であり、重要なデータへのアクセスを妨げます。 一般に、コモディティ ランサムウェアは、デバイスに感染するウイルスのように広がり、マルウェアの修復のみを必要とします。 人が操作するランサムウェアは、組織のオンプレミスまたはクラウド IT インフラストラクチャに侵入し、自分たちの権限を昇格し、ランサムウェアを重要なデータに展開するサイバー犯罪者による積極的な攻撃の結果です。

攻撃が完了すると、攻撃者は、削除されたファイルの返却、暗号化されたファイルの暗号化解除キー、またはダーク Web またはパブリック インターネットに機密データを解放しないという約束と引き換えに、被害者に金銭を要求します。 また、人が操作するランサムウェアを使用して、産業生産に必要なコンピューターやプロセスなどの重要なコンピューターやプロセスをシャットダウンしたり、身代金を支払って損害を修正したり、組織が自身の損害を修復したりするまで、通常の業務を停止することができます。

人が操作するランサムウェア攻撃は、すべてのサイズの企業にとって壊滅的であり、クリーンアップが困難であり、将来の攻撃から保護するために完全に敵対的な立ち退きを必要とします。 コモディティ ランサムウェアとは異なり、人が操作するランサムウェアは、最初の身代金要求後も企業の業務を脅かし続ける可能性があります。

>[!Note]
>Microsoft 365 テナントに対するランサムウェア攻撃の前提は、攻撃者がテナントに対して有効なユーザー アカウント資格情報を持ち、ユーザー アカウントに対して許可されているすべてのファイルとリソースにアクセスできると想定していることです。 有効なユーザー アカウント資格情報を持たない攻撃者は、Microsoft 365 の既定の暗号化と強化された暗号化によって暗号化され保存されたデータを解読する必要があります。 詳細については、「[暗号化とキー管理の概要](/compliance/assurance/assurance-encryption)」を参照してください。 
>

Microsoft 製品全体のランサムウェア保護の詳細については、次の 「[追加のランサムウェアリソース](#additional-ransomware-resources)」 を参照してください。

## <a name="security-in-the-cloud-is-a-partnership"></a>クラウドのセキュリティはパートナーシップ

Microsoft クラウド サービスのセキュリティは、お客様と Microsoft のパートナーシップです。

- Microsoft クラウド サービスは信頼とセキュリティの基盤の上に構築されます。 Microsoft が提供するセキュリティ制御と機能は、お客様のデータとアプリケーションの保護に役立ちます。
- お客様はご自分のデータと ID を所有しており、それらとオンプレミス リソースのセキュリティ、およびご自分が制御しているクラウド コンポーネントのセキュリティを保護する責任を担っています。

これらの機能と責任を組み合わせることで、ランサムウェア攻撃に対する最高の保護を提供できます。

## <a name="ransomware-mitigation-and-recovery-capabilities-provided-with-microsoft-365"></a>Microsoft 365 が提供するランサムウェアの軽減と回復機能、

Microsoft 365 テナントに侵入したランサムウェア攻撃者は、次の方法で企業から身代金を受け取る可能性があります。

- ファイルまたはメールの削除
- 存在するファイルの暗号化
- テナント外でのファイルのコピー (データの外部流出)

ただし、Microsoft 365 オンライン サービスには、ランサムウェア攻撃から顧客データを保護するための多くの組み込みの機能とコントロールがあります。 次のセクションでは、概要を説明します。 Microsoft が顧客データを保護する方法の詳細については、「[Microsoft 365 のマルウェアとランサムウェアからの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)」を参照してください。

>[!Note]
>Microsoft 365 テナントに対するランサムウェア攻撃の前提は、攻撃者がテナントに対して有効なユーザー アカウント資格情報を持ち、ユーザー アカウントに対して許可されているすべてのファイルとリソースにアクセスできると想定していることです。 有効なユーザー アカウント資格情報を持たない攻撃者は、Microsoft 365 の既定の暗号化と強化された暗号化によって暗号化され保存されたデータを解読する必要があります。 詳細については、「[暗号化とキー管理の概要](/compliance/assurance/assurance-encryption)」を参照してください。 
>

### <a name="deleting-files-or-email"></a>ファイルまたはメールの削除

次の SharePoint および OneDrive for Business のファイルは、次の方法で保護されます。

- バージョン管理 

   Microsoft 365 は、既定で最低でも 500 以上のバージョンのファイルを保持し、それ以上のファイルを保持するように構成できます。 

   セキュリティとヘルプデスク スタッフの負担を最小限に抑えるために、[以前のバージョンのファイルを復元する](https://support.microsoft.com/office/restore-a-previous-version-of-an-item-or-file-in-sharepoint-f66dbda0-81f4-4d1e-b08c-793265c58934)方法についてユーザーにトレーニングします。

- ごみ箱

   ランサムウェアがファイルの新しい暗号化されたコピーを作成し、古いファイルを削除する場合、顧客は 93 日間の間にファイルをごみ箱から復元することが可能です。 93 日以降の場合でも、Microsoft がデータを回復できる 14 日間の猶予があります。 
  
   セキュリティとヘルプデスク スタッフの負担を最小限に抑えるために、[ごみ箱からファイルを復元する](https://support.microsoft.com/en-us/office/restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)方法についてユーザーにトレーニングします。

- [ファイルの復元](https://techcommunity.microsoft.com/t5/microsoft-onedrive-blog/announcing-new-onedrive-for-business-feature-files-restore/ba-p/147436)

   管理者とエンド ユーザーが過去 30 日間の任意の時点からファイルを復元できる SharePoint および OneDrive の完全なセルフサービス回復ソリューション。

   セキュリティと IT ヘルプデスク スタッフの負担を最小限に抑えるために、ユーザーに対して、[SharePoint と OneDrive の保持](/microsoft-365/compliance/retention-policies-sharepoint)の方法についてユーザーにトレーニングします。


OneDrive のファイルと SharePoint のファイルについては、大量攻撃に遭った場合、Microsoft は最大 14 日前までの時点にロールバックできます。

電子メールは次の方法で保護されています。

- [単一アイテムの回復](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery) とメールボックスの保持。不注意または悪意のある早期削除時にメールボックス内のアイテムを回復できます。 既定では、14 日以内に削除されたメール メッセージをロールバックできます。最大 30 日間は構成可能です。

- [保持ポリシー](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) を使用すると、構成済みの保持期間の間、変更できないメールのコピーを保持できます。

### <a name="encrypting-files-in-place"></a>存在するファイルの暗号化

前に説明したように、次の SharePoint とOneDrive for Business のファイルは、悪意のある暗号化から保護されています。

- バージョン管理
- ごみ箱
- アイテム保管ライブラリ

詳細については、「[Microsoft 365 でのデータ破損の処理](/compliance/assurance/assurance-dealing-with-data-corruption)」を参照してください。

### <a name="copying-files-outside-your-tenant"></a>テナント外でのファイルのコピー 

次の方法で、ランサムウェア攻撃者がテナント外でファイルをコピーするのを防ぐことが可能です。

- [データ損失防止 (DLP) ](/microsoft-365/compliance/dlp-learn-about-dlp)ポリシー

    データの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。

    - そのデータには、地域のプライバシー規制を遵守するための個人識別情報 (PII) などの個人情報が含まれます。

    - 秘密度ラベルに基づく組織の機密情報。

- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)

    ファイルなどの機密情報のダウンロードをブロックします。 

    また、[Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/tutorial-dlp#how-to-discover-and-protect-sensitive-information-in-your-organization)を使用して、ユーザーとアプリケーション間の情報のフローをリアルタイムで監視することもできます。

## <a name="whats-in-this-solution"></a>このソリューションの機能

このソリューションでは、Microsoft 365 の保護と軽減機能、構成、および継続的な操作を展開して、ランサムウェア攻撃者が Microsoft 365 テナント内の重要なデータを使用して身代金要求に対して組織を保持する能力を最小限に抑える手順を実行します。

![Microsoft 365 によるランサムウェアから保護するための手順](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step-grid.png)

このソリューションの手順は次のとおりです。

1. [セキュリティ 基準を構成する](ransomware-protection-microsoft-365-security-baselines.md)
2. [攻撃の検出と応答を展開する](ransomware-protection-microsoft-365-attack-detection-response.md)
3. [ID の保護](ransomware-protection-microsoft-365-identities.md)
4. [デバイスを保護する](ransomware-protection-microsoft-365-devices.md)
5. [情報の保護](ransomware-protection-microsoft-365-information.md)

Microsoft 365 テナント用にデプロイされたソリューションの 5 つの手順を次に示します。

![Microsoft 365 テナントのためのランサムウェア保護](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture.png)


## <a name="microsoft-365-capabilities-and-features"></a>Microsoft 365 の機能と機能

ランサムウェア攻撃から Microsoft 365 テナントを保護するには、このソリューションの手順用の Microsoft 365 の能力と機能を使用します。

### <a name="1-security-baseline"></a>1. セキュリティ基準

| 機能 | 説明 | 役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
| Microsoft セキュア スコア |  Microsoft 365 テナントのセキュリティの姿勢を測定する | セキュリティ構成を評価し、改善点を提案します。 | Microsoft 365 E3 または Microsoft 365 E5 |
| 攻撃面の減少ルール | さまざまな構成設定を使用して、サイバー攻撃に対する組織の脆弱性を軽減する | 疑わしいアクティビティと脆弱なコンテンツをブロックします。 | Microsoft 365 E3 または Microsoft 365 E5 |
| Exchange のメール設定 |  メール ベースの攻撃に対する組織の脆弱性を軽減するサービスを有効にする | フィッシングなどのメール ベースの攻撃を通じてテナントへの初期アクセスを防止します。  | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Windows、Microsoft Edge、およびMicrosoft 365 Apps for Enterprise の設定 | 広く知られ、証明済の業界標準のセキュリティ構成を提供します | Windows、Edge、Microsoft 365 Apps for Enterprise による攻撃を防ぎます。 | Microsoft 365 E3 または Microsoft 365 E5 |
|

### <a name="2-detection-and-response"></a>2. 検出と応答

| 機能 | 説明 | 検出と応答に役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
| Microsoft 365 Defender | 信号を結合し、機能を統合して 1 つのソリューションに統合する <br><br> セキュリティ専門家が脅威信号を一緒に縫い合わせ、脅威の範囲と影響全体を特定します <br><br> 攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復するためのアクションを自動化します。 | インシデント。これは、攻撃を構成するアラートとデータを組み合わせたものです。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
| Microsoft Defender for Identity |  クラウドベースのセキュリティ インターフェイスを介して組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを識別、検出、および調査するには、オンプレミスの Active Directory ドメイン サービス (AD DS) 信号を使用します。 | AD DS アカウントの資格情報の侵害。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
| Microsoft Defender for Office 365 | メール メッセージ、リンク (URL)、共同作業ツールによってもたらされる悪意のある脅威から組織を保護します。 <br><br> マルウェア、フィッシング、スプーフィング、その他の攻撃の種類から保護する | フィッシング攻撃。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
| Microsoft Defender for Endpoint | エンドポイント (デバイス) 全体の高度な脅威の検出と対応を可能にします | マルウェアのインストールとデバイスの侵害。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
| Azure Active Directory(Azure AD) ID 保護 | ID ベースのリスクの検出と修復、およびそれらのリスクの調査を自動化します | Azure AD アカウントと特権のエスカレーションに対する資格情報の侵害。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
| Microsoft Cloud App Security | Microsoft およびサード パーティのクラウド サービス全体で検出、調査、ガバナンスを行うクラウド アクセス セキュリティ ブローカー | 横方向の動きとデータ流出。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
|

### <a name="3-identities"></a>3. ID

| 機能 | 説明 | 予防に役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
|Azure AD パスワード保護|共通のリストとカスタム エントリからのパスワードをブロックします。|クラウドまたはオンプレミスのユーザー アカウントのパスワードの決定。|Microsoft 365 E3 または Microsoft 365 E5|
|条件付きアクセスが適用されている MFA|条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。|資格情報の侵害とアクセス。|Microsoft 365 E3 または Microsoft 365 E5|
|リスクベースの条件付きアクセスが適用されている MFA|Azure AD Identity Protection を使用したユーザー サインインのリスクに基づいて MFA を要求します。 |資格情報の侵害とアクセス。|Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3|
|

### <a name="4-devices"></a>4. デバイス

デバイスとアプリの管理

| 機能 | 説明 | 予防に役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
| Microsoft Intune | デバイスと、デバイス上で実行されるアプリケーションを管理する  | デバイスまたはアプリの侵害とアクセス。 | Microsoft 365 E3 または E5 |
|  |  |  |  |

Windows 10 デバイス (プレビュー)

| 機能 | 説明 | 役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
| Microsoft Defender ファイアウォール | ホスト ベースのファイアウォールを提供します。  | 受信、未承諾のネットワーク トラフィックからの攻撃を防ぎます。 | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Defender ウイルス対策 | 機械学習、ビッグ データ分析、詳細な脅威耐性調査、Microsoft クラウド インフラストラクチャを使用したデバイス (エンドポイント) のマルウェア対策保護を提供します。 | マルウェアのインストールと実行を防止します。 | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Defender SmartScreen | フィッシングやマルウェアの Web サイトやアプリケーション、悪意のある可能性のあるファイルのダウンロードから保護します。 | サイト、ダウンロード、アプリ、ファイルを確認するときにブロックまたは警告を表示します。 | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Defender for Endpoint | デバイス (エンドポイント) 間の高度な脅威を防止、検出、調査、および対応するのに役立ちます。 | ネットワーク改ざんから保護します。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
|  |  |  |  |

### <a name="5-information"></a>5. 情報

| 機能 | 説明 | 役立ちます... | ライセンス |
|:-------|:-----|:-------|:-------|
| コントロールされたフォルダー アクセス | 既知の信頼できるアプリの一覧に対してアプリをチェックしてデータを保護する | ファイルがランサムウェアによって変更または暗号化されないようにします。 | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Information Protection | 身代金要求の対象となっている情報に対して、秘密度ラベルの適用が可能 | 流出した情報の使用を防ぎます。 | Microsoft 365 E3 または Microsoft 365 E5 |
| データ損失防止 (DLP) | 機密データを保護し、ユーザーによる不適切な共有を防止することでリスクを軽減する | データ流出を防止する | Microsoft 365 E3 または Microsoft 365 E5 |
| Microsoft Cloud App Security | 検出、調査、ガバナンスのためのクラウド アクセス セキュリティ ブローカー | 横方向の動きを検出し、データ流出を防ぎます。 | Microsoft 365 E5 セキュリティ アドオン付きのMicrosoft 365 E5 または Microsoft 365 E3 |
|

## <a name="impact-on-users-and-change-management"></a>ユーザーへの影響と変更管理

追加のセキュリティ機能を展開し、Microsoft 365 テナントの要件とセキュリティ ポリシーを実装すると、ユーザーに影響を与える可能性があります。 

たとえば、組織内のすべてのユーザーのチームをより簡単に作成するのではなく、ユーザー アカウントの一覧をメンバーとして使用して、特定の用途に対して新しいチームを作成する必要がある新しいセキュリティ ポリシーを適用できます。 これにより、ランサムウェア攻撃者が攻撃者の侵害されたユーザー アカウントで利用できないチームを探索し、その後の攻撃でそのチームのリソースをターゲットにすることを予防する助けとなります。

この基礎ソリューションは、必要な変更管理を実行するために、新しい構成や推奨されるセキュリティ ポリシーがユーザーに影響を与える可能性がある場合を識別します。

## <a name="next-steps"></a>次の手順

次の手順を使用して、Microsoft 365 テナントの包括的な保護を展開します。

1. [セキュリティ 基準を構成する](ransomware-protection-microsoft-365-security-baselines.md)
2. [攻撃の検出と応答を展開する](ransomware-protection-microsoft-365-attack-detection-response.md)
3. [ID の保護](ransomware-protection-microsoft-365-identities.md)
4. [デバイスを保護する](ransomware-protection-microsoft-365-devices.md)
5. [情報の保護](ransomware-protection-microsoft-365-information.md)

[![Microsoft 365 によるランサムウェア保護の手順 1 ](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step1.png)](ransomware-protection-microsoft-365-security-baselines.md)

## <a name="additional-ransomware-resources"></a>その他のランサムウェア リソース

Microsoft の主な情報:

- [ランサムウェアの脅威の増大](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/)、2021 年 7月 20 日付け Microsoft On the Issues のブログ投稿
- [人が操作するランサムウェア](/security/compass/human-operated-ransomware)
- [ランサムウェアや強要から迅速に保護する](/security/compass/protect-against-ransomware)
- [最新の Microsoft セキュリティ インテリジェンス レポート](https://www.microsoft.com/securityinsights/)( 22-24 ページを参照してください)
- **ランサムウェア: Microsoft 365 Defender ポータルの **脅威分析** ノードの蔓延する継続的な脅威** に関するレポート (これらの「[ライセンス要件](/microsoft-365/security/defender/prerequisites#licensing-requirements)」 を参照ください)

Microsoft 365:

- [ランサムウェア攻撃から回復する](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [マルウェアと ランサムウェアからの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [ランサムウェアから Windows 10 PC を保護する](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online でのランサムウェアの処理](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)

Microsoft 365 Defender:

- [高度な検索でランサムウェアを検索する](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure

- [ランサムウェア攻撃に対する Azure 防御](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [ランサムウェアから保護するためのバックアップと復元の計画](/security/compass/backup-plan-to-protect-against-ransomware)
- [Microsoft Azure バックアップを使用してランサムウェアから保護する](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 分のビデオ)
- [体系的な ID 侵害からの回復](/azure/security/fundamentals/recover-from-identity-compromise)
- [Azure Sentinel での高度な多段階攻撃検出](/azure/sentinel/fusion#ransomware)
- [Azure Sentinel でのランサムウェアのフュージョン検出](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Cloud App Security:

-  [Cloud App Security で異常検出ポリシーを作成する](/cloud-app-security/anomaly-detection-policy)

Microsoft Security チームのブログ投稿:

- [ランサムウェアを防止して回復するための 3 つの手順 (2021 年 9 月)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [サイバーセキュリティ リスクを理解することで回復力を高める パート 4—現在の脅威をナビゲートする(2021 年 5 月)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  「**ランサムウェア**」セクションを参照 してください。

- [人が操作するランサムウェア攻撃: 予防可能な災害 (2020 年 3 月)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  実際の攻撃の攻撃チェーン分析が含まれます。

- [ランサムウェアの応答 - 支払うべきか、支払わざるべきか? (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro のランサムウェア攻撃に対する透明性のある対応 (2019 年 12 月)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
