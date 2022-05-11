---
title: Microsoft Purview Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Microsoft Purview Information Protection 機能を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報を保護できます。
ms.openlocfilehash: b055e71ee6c22cc9804b82a36f339a73675ce914
ms.sourcegitcommit: f723ebbc56db8013598a88b0d7f13214d9d3eb10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2022
ms.locfileid: "65294649"
---
# <a name="protect-your-sensitive-data-with-microsoft-purview"></a>Microsoft Purview を使用して機密データを保護する

>*[Microsoft 365 セキュリティとコンプライアンスのライセンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

> [!TIP]
> *9 つの Microsoft Purview ソリューションすべてのプレミアム バージョンを無料で試すことができることをご存知ですか?* 90 日間の Purview ソリューション試用版を使用して、堅牢な Purview 機能が組織のコンプライアンス ニーズを満たすのにどのように役立つかを調べてください。 Microsoft 365 E3 および Office 365 E3 のお客様は、[Microsoft Purview コンプライアンス ポータルの試用版ハブ](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef)から今すぐ開始できます。 [サインアップできるユーザーと試用版の使用条件](compliance-easy-trials.md)の詳細について説明します。

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**Microsoft Purview Information Protection** (以前の Microsoft Information Protection) の機能を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報の検出、分類、保護が可能になります。

これらの情報保護機能は、[データを把握](#know-your-data)し、[データを保護](#protect-your-data)し、[データの損失を防止する](#prevent-data-loss)ためのツールを提供しています。

![Microsoft Purview Information Protection が機密データの検出、分類、および保護にどのように役立つかを示す画像。](../media/powered-by-intelligent-platform.png)

次のセクションを使用して、使用可能な機能の詳細と、各機能の使用を開始する方法について説明します。 ただし、ガイド付きデプロイを探している場合は、「[Microsoft Purview による情報保護ソリューションの展開](information-protection-solution.md)」を参照してください。

コンプライアンス要件または規制要件に関するデータの管理については、「[Microsoft Purview を使用してデータを管理する](manage-data-governance.md)」を参照してください。

## <a name="know-your-data"></a>データを把握する

データの状況を把握し、ハイブリッド環境全体にわたって機密データを識別するには、次の機能を使用します:

|機能|解決される問題|作業の開始|
|:------|:------------|:--------------------|
|[機密情報の種類](sensitive-information-type-learn-about.md)| 組み込みまたはカスタムの正規表現または関数を使用して、機密データを識別します。 裏付けとなる証拠には、キーワード、信頼水準、および近接性が含まれます。| [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)|
|[トレーニング可能な分類子](classifier-learn-about.md)| アイテム内の要素を識別する (パターン マッチング) のではなく、関心のあるデータの例を使用して機密性の高いデータを識別します。 組み込みの分類子を使用することも、独自のコンテンツを使用して分類子をトレーニングすることもできます。| [トレーニング可能な分類子の使用を開始する](classifier-get-started-with.md) |
|[データの分類](data-classification-overview.md) | 組織内の、秘密度ラベルまたは保持ラベルを有するアイテムまたは分類済みアイテムのグラフィカルな ID です。 この情報を使用して、ユーザーがこれらのアイテムに対して実行しているアクションに関する分析情報を得ることもできます。 | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md) <p> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、視覚的なマーキングなどを含む柔軟な保護アクションを適用するには、次の機能を使用します。

|機能|解決される問題|作業の開始|
|:------|:------------|---------------------|
|[秘密度ラベル](sensitivity-labels.md)| 組織の内外を移動するデータを保護する、アプリ、サービス、デバイスにまたがる単一のラベル付けソリューションです。 <br /><br /> サンプル シナリオ: <br />- [Office アプリの秘密度ラベルを管理する](sensitivity-labels-office-apps.md) <br />- [ドキュメントと電子メールの暗号化](encryption-sensitivity-labels.md) <br />-  [Power BIでラベルを適用および表示する](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> 秘密度ラベルでサポートされているシナリオの包括的なリストについては、「作業の開始」のドキュメントを参照してください。|[秘密度ラベルの使用を開始する](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 統合ラベル付けクライアント](/azure/information-protection/rms-client/aip-clientv2)| Windows コンピューターの場合、ラベル付けを エクスプローラー と PowerShell に拡張し、必要に応じて Office アプリの追加機能を使用します| [Azure Information Protection 統合ラベル付けクライアント管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[二重キー暗号化](double-key-encryption.md)| どのような状況においても、保護されたコンテンツを復号化できるのは自分の組織だけです。また、規制要件により、暗号化キーを地理的な境界内に保持する必要があります。 | [二重キー暗号化の展開](double-key-encryption.md#deploy-dke)|
|[Office 365 Message Encryption (OME)](ome.md)| メール メッセージと添付ドキュメントはいずれのデバイス上のいずれのユーザーに送信される場合も暗号化されるため、承認された受信者のみがメールの情報を読むことができます。 <br /><br />  サンプル シナリオ: [Advanced Message Encryption を使用して暗号化されたメールを無効にする](revoke-ome-encrypted-mail.md) | [新しい Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)|
|[カスタマー キーによるサービスの暗号化](customer-key-overview.md) | 承認されていないシステムや担当者によるデータの閲覧を防止し、Microsoft データセンターの BitLocker ディスク暗号化を補完します。 | [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|これは、SharePoint リストとライブラリを保護するもので、ユーザーがドキュメントをチェックアウトした際に、ダウンロードされたファイルが保護されるようになります。これにより、管理者が指定したポリシーに基づき、承認されているユーザーのみがファイルを閲覧したり使用したりできます。 | [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)|
[Rights Management コネクタ](/azure/information-protection/deploy-rms-connector) |Exchange や SharePoint Server を使用する既存のオンプレミスの展開か、または Windows Server とファイル分類インフラストラクチャ (FCI) を実行するファイル サーバーを保護する場合に限ります。 | [RMS コネクタを展開する手順](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection 統合ラベル付けスキャナー](/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータ ストア内にある機密情報の検出、ラベル付け、保護を行います。 | [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)| クラウド上のデータ ストア内にある機密情報の検出、ラベル付け、保護を行います。 | [クラウドに保存されている規制対象データや機密データを検出し、分類し、ラベル付けし、保護する](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Purview データ マップ](/azure/purview/overview) |機密データを識別し、Microsoft Purview データ マップ アセットのコンテンツに自動ラベル付けを適用します。 これには、Azure Data Lake や Azure Files などのストレージ内のファイル、および Azure SQL DB や Cosmos DB の列などのスキーマ化されたデータが含まれます。 |[Microsoft Purview データ マップでのラベル付け](/azure/purview/create-sensitivity-label) |
|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|秘密度ラベルの適用をサードパーティ製アプリやサービスに拡大します。 <br /><br />  サンプル シナリオ: [秘密度ラベルの設定と取得 (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft Information Protection (MIP) SDK の設定と構成](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報が誤って過度に共有されてしまうのを防止するために、次の機能を使用します。


|機能|解決される問題|作業の開始|
|:------|:------------|:---------------------|
|[Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)| 機密アイテムの意図しない共有の防止をサポートします。 | [既定の DLP ポリシーの使用を開始する](get-started-with-the-default-dlp-policy.md)|
|[エンドポイントのデータ損失防止](endpoint-dlp-learn-about.md)| Windows 10 コンピューターで使用され共有されるアイテムに DLP 機能を拡張します。 | [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)|
|[Microsoft Compliance Extension](dlp-chrome-learn-about.md) | Chrome ブラウザーに DLP 機能を拡張します | [Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md)|
|[Microsoft Purview のデータ損失防止のオンプレミス スキャナー (プレビュー)](dlp-on-premises-scanner-learn.md)|ファイル アクティビティの DLP 監視とそれらのファイルの保護アクションを、オンプレミスのファイル共有と SharePoint フォルダーおよびドキュメント ライブラリに拡張します。|[Microsoft Purview のデータ損失防止のオンプレミス スキャナー (プレビュー) の使用を開始する](dlp-on-premises-scanner-get-started.md)|
|[Microsoft Teams のチャットやチャネル メッセージでの機密情報の保護](dlp-microsoft-teams.md) | 一部の DLP 機能を Teams のチャットおよびチャネル メッセージに拡張します | [Microsoft Teams の既定のデータ損失防止ポリシーについての詳細情報 (プレビュー)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft Purview Information Protection のライセンス要件は、このページにリストされている各機能のライセンス要件を設定するのではなく、使用するシナリオと機能によって異なります。 Microsoft Purview Information Protection のライセンス要件とオプションを理解するには、[セキュリティとコンプライアンスに関するMicrosoft 365ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)の **情報保護** セクションと、機能レベルのライセンス要件に関す [PDF ダウンロード](https://go.microsoft.com/fwlink/?linkid=2139145)を参照してください。
