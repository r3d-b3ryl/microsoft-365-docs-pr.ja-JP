---
title: Microsoft 365 の Microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Microsoft Information Protection (MIP) を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報を保護できます。
ms.openlocfilehash: 76e2da01dd9fbcbb7d053b61b515aeb998d86c5147893a822dfa2695e43f58a4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53860792"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 の Microsoft Information Protection

>*[Microsoft 365 セキュリティとコンプライアンスのライセンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft Information Protection (MIP) を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報の検出、分類、保護が可能になります。

MIP 機能は Microsoft 365 コンプライアンスに含まれており、[データを把握](#know-your-data)し、[データを保護](#protect-your-data)し、[データの損失を防止する](#prevent-data-loss)ためのツールを提供しています。

![MIP が機密性の高いデータの検出、分類、保護にどのように役立つかについての画像](../media/powered-by-intelligent-platform.png)

データの管理については、「[Microsoft 365 の Microsoft 情報ガバナンス](manage-Information-governance.md)」を参照してください。

## <a name="know-your-data"></a>データを把握する

> [!NOTE]
> Azure Purview でのデータの分類およびラベル付けの詳細については、現在プレビューですが、「[Azure Purviewにあるコンテンツに自動的にラベルを付ける](/azure/purview/create-sensitivity-label)」を参照し てください。

データの状況を把握し、ハイブリッド環境全体にわたって重要なデータを識別するには、次の機能を使用します:

|機能|解決される問題|作業の開始|
|:------|:------------|:--------------------|
|[機密情報の種類](sensitive-information-type-learn-about.md)| 組み込みまたはカスタムの正規表現または関数を使用して、機密データを識別します。 裏付けとなる証拠には、キーワード、信頼水準、および近接性が含まれます。| [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)|
|[トレーニング可能な分類子](classifier-learn-about.md)| アイテム内の要素を識別する (パターン マッチング) のではなく、関心のあるデータの例を使用して機密性の高いデータを識別します。 組み込みの分類子を使用することも、独自のコンテンツを使用して分類子をトレーニングすることもできます。| [トレーニング可能な分類子の使用を開始する](classifier-get-started-with.md) |
|[データの分類](data-classification-overview.md) | 組織内の、秘密度ラベルまたは保持ラベルを有するアイテムまたは分類済みアイテムのグラフィカルな ID です。 この情報を使用して、ユーザーがこれらのアイテムに対して実行しているアクションに関する分析情報を得ることもできます。 | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md) <p> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、視覚的なマーキングなどを含む柔軟な保護アクションを適用するには、次の機能を使用します。

|機能|解決される問題|作業の開始|
|:------|:------------|---------------------|
|[秘密度ラベル](sensitivity-labels.md)| 組織の内外を移動するデータをラベル付けして保護する、アプリ、サービス、デバイスにまたがる単一のソリューションです。 <p> サンプル シナリオ: <p> [Office アプリの秘密度ラベルを管理する](sensitivity-labels-office-apps.md) <p> [ドキュメントとメールを暗号化する](encryption-sensitivity-labels.md) <p> [Power BI でラベルを適用して表示する](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> 秘密度ラベルのシナリオの包括的なリストについては、"作業の開始" のドキュメントを参照してください。|[秘密度ラベルの使用を開始する](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 統合ラベル付けクライアント](/azure/information-protection/rms-client/aip-clientv2)| Windows コンピューターの場合、秘密度ラベルが拡張され、すべてのファイルの種類に対するエクスプローラーや PowerShell からのラベル付けや保護を含む機能が追加されています <p> 追加機能の例: [Azure Information Protection 統合ラベル付けクライアントのカスタム構成](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 統合ラベル付けクライアント管理者ガイド](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[二重キー暗号化](double-key-encryption.md)| どのような状況においても、保護されたコンテンツを復号化できるのは自分の組織だけです。また、規制要件により、暗号化キーを地理的な境界内に保持する必要があります。 | [二重キー暗号化の展開](double-key-encryption.md#deploy-dke)|
|[Office 365 Message Encryption (OME)](ome.md)| メール メッセージと添付ドキュメントはいずれのデバイス上のいずれのユーザーに送信される場合も暗号化されるため、承認された受信者のみがメールの情報を読むことができます。 <p> サンプル シナリオ: [Advanced Message Encryption を使用して暗号化されたメールを無効にする](revoke-ome-encrypted-mail.md) | [新しい Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)|
|[カスタマー キーによるサービスの暗号化](customer-key-overview.md) | 承認されていないシステムや担当者によるデータの閲覧を防止し、Microsoft データセンターの BitLocker ディスク暗号化を補完します。 | [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|これは、SharePoint リストとライブラリを保護するもので、ユーザーがドキュメントをチェックアウトした際に、ダウンロードされたファイルが保護されるようになります。これにより、管理者が指定したポリシーに基づき、承認されているユーザーのみがファイルを閲覧したり使用したりできます。 | [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)|
[Rights Management コネクタ](/azure/information-protection/deploy-rms-connector) |Exchange や SharePoint Server を使用する既存のオンプレミスの展開か、または Windows Server とファイル分類インフラストラクチャ (FCI) を実行するファイル サーバーを保護する場合に限ります。 | [RMS コネクタを展開する手順](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection 統合ラベル付けスキャナー](/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータ ストア内にある機密情報の検出、ラベル付け、保護を行います。 | [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| クラウド上のデータ ストア内にある機密情報の検出、ラベル付け、保護を行います。 | [クラウドに保存されている規制対象データや機密データを検出し、分類し、ラベル付けし、保護する](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|秘密度ラベルの適用をサードパーティ製アプリやサービスに拡大します。 <p> サンプル シナリオ: [秘密度ラベルの設定と取得 (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft Information Protection (MIP) SDK の設定と構成](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報が誤って過度に共有されてしまうのを防止するために、次の機能を使用します。


|機能|解決される問題|作業の開始|
|:------|:------------|:---------------------|
|[データ損失防止](dlp-learn-about-dlp.md)| 機密アイテムの意図しない共有の防止をサポートします。 | [既定の DLP ポリシーの使用を開始する](get-started-with-the-default-dlp-policy.md)|
|[エンドポイントのデータ損失防止](endpoint-dlp-learn-about.md)| Windows 10 コンピューターで使用され共有されるアイテムに DLP 機能を拡張します。 | [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)|
|[Microsoft Compliance Extension](dlp-chrome-learn-about.md) | Chrome ブラウザーに DLP 機能を拡張します | [Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md)|
|[Microsoft 365 のデータ損失防止のオンプレミス スキャナー (プレビュー)](dlp-on-premises-scanner-learn.md)|ファイル アクティビティの DLP 監視とそれらのファイルの保護アクションを、オンプレミスのファイル共有と SharePoint フォルダーおよびドキュメント ライブラリに拡張します。|[Microsoft 365 のデータ損失防止のオンプレミス スキャナー (プレビュー) の使用を開始する](dlp-on-premises-scanner-get-started.md)|
|[Microsoft Teams のチャットやチャネル メッセージでの機密情報の保護](dlp-microsoft-teams.md) | 一部の DLP 機能を Teams のチャットおよびチャネル メッセージに拡張します | [Microsoft Teams の既定のデータ損失防止ポリシーについての詳細情報 (プレビュー)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>ライセンスの要件

MIP のライセンス要件は、このページにリストされている各機能のライセンス要件を設定するのではなく、使用するシナリオと機能によって異なります。 MIP のライセンス要件とオプションを理解するには、Microsoft 365 ライセンス ドキュメントの「[情報保護](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」セクションを参照し、関連する PDF または Excel をダウンロードしてください。
