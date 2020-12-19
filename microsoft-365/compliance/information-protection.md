---
title: Microsoft 365 の Microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: Microsoft Information Protection (MIP) を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報を保護できます。
ms.openlocfilehash: 2a1ec47ce888dc6d31868d65f9c4c113fa9b968c
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709509"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 の Microsoft Information Protection

>*[Microsoft 365 セキュリティとコンプライアンスのライセンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft Information Protection (MIP) を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報の検出、分類、保護が可能になります。

MIP 機能は Microsoft 365 コンプライアンスに含まれており、[データを把握](#know-your-data)し、[データを保護](#protect-your-data)し、[データの損失を防止する](#prevent-data-loss)ためのツールを提供しています。

![MIP が機密性の高いデータの検出、分類、保護にどのように役立つかについての画像](../media/powered-by-intelligent-platform.png)

データの管理については、「[Microsoft 365 の Microsoft 情報ガバナンス](manage-Information-governance.md)」を参照してください。

## <a name="know-your-data"></a>データを把握する

> [!NOTE]
> Azure Purview でのデータの分類およびラベル付けの詳細については、現在プレビューですが、「[Azure Purviewにあるコンテンツに自動的にラベルを付ける](https://docs.microsoft.com/azure/purview/create-sensitivity-label)」を参照し てください。
> 
> この新しいリリースの詳細については、ブログ投稿「[Microsoft Information Protection および Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481)」を参照してください。



データの状況を把握し、ハイブリッド環境全体にわたって重要なデータを識別するには、次の機能を使用します:
 
|機能|解決される問題|作業の開始|
|:------|:------------|:--------------------|:-----------------------------|
|[機密情報の種類](sensitive-information-type-entity-definitions.md)| キーワード、信頼度レベル、近接度などの補強証拠とともに、組み込みの正規表現、カスタムの正規表現、関数を使用して、機密データを識別します。| [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)|
|[トレーニング可能な分類子 (プレビュー)](classifier-learn-about.md)| 組み込みの分類子のいずれかを使用したり、独自のコンテンツを使用して分類子をトレーニングしたりして、データを分類することができます | [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-get-started-with.md) |
|[データの分類](data-classification-overview.md) | 秘密度ラベルや保持ラベルが付けられているアイテムや、機密情報の種類として組織内で分類されているアイテムと、それらに対するユーザーのアクションを識別します  | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md)<br /><br /> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、視覚的なマーキングなどを含む柔軟な保護アクションを適用するには、次の機能を使用します。

|機能|解決される問題|作業の開始|
|:------|:------------|---------------------|:----------------------------|
|[秘密度ラベル](sensitivity-labels.md)| 組織の内外を移動するデータをラベル付けして保護する、アプリ、サービス、デバイスにまたがる単一のソリューション <br /><br />シナリオの例: [Power BI  でラベルの適用と表示をし、サービスの外部に保存されたデータを保護する](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[秘密度ラベルの使用を開始する](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows コンピューターの場合、秘密度ラベルが拡張され、すべてのファイルの種類に対するエクスプローラーや PowerShell からのラベル付けや保護を含む機能が追加されています<br /><br /> 追加機能の例: [Azure Information Protection 統合ラベル付けクライアントのカスタム構成](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 統合ラベル付けクライアント管理者ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[二重キー暗号化](double-key-encryption.md)| どのような状況においても、保護されたコンテンツを復号化できるのは自分だけです。また規制要件においては、地理的な境界内に暗号化キーを保持する必要があります | [二重キー暗号化の展開](double-key-encryption.md#deploy-dke)|
|[Office 365 Message Encryption (OME)](ome.md)| 任意のデバイス上の任意のユーザーに送信されるメール メッセージと添付ドキュメントを暗号化することで、承認された受信者のみがメールの情報を読むことができます  <br /><br />サンプル シナリオ: [Advanced Message Encryption を使用して暗号化されたメールを無効にする](revoke-ome-encrypted-mail.md) | [新しい Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)|
|[カスタマー キーによるサービスの暗号化](customer-key-overview.md) | 承認されていないシステムや担当者によるデータの閲覧を防止し、Microsoft データセンターの BitLocker ディスク暗号化を補完します | [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|SharePoint リストとライブラリを保護し、ユーザーがドキュメントをチェックアウトするときにダウンロードされるファイルを保護し、指定したポリシーに従って承認されているユーザーのみがファイルを閲覧したり使用したりできるようにします | [SharePoint 管理センターで Information Rights Management (IRM) を設定する](set-up-irm-in-sp-admin-center.md)|
[Rights Management コネクタ](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Exchange や SharePoint Server を使用する既存のオンプレミスの展開か、または Windows Server とファイル分類インフラストラクチャ (FCI) を実行するファイル サーバーを保護する場合に限ります | [RMS コネクタを展開する手順](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection 統合ラベル付けスキャナー](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータ ストア内にある機密情報の検出、ラベル付け、保護 | [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| クラウド上のデータ ストア内にある機密情報の検出、ラベル付け、保護 | [クラウドに保存されている規制対象データや機密データを検出し、分類し、ラベル付けし、保護する](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|秘密度ラベルの適用をサード パーティ製アプリやサービスに拡大する  <br /><br /> サンプル シナリオ: [秘密度ラベルの設定と取得 (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft Information Protection (MIP) SDK の設定と構成](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報が誤って過度に共有されてしまうのを防止するために、次の機能を使用します。


|機能|解決される問題|作業の開始|
|:------|:------------|:---------------------|:-----------------------------|
|[データ損失防止 (DLP)](data-loss-prevention-policies.md)| 機密アイテムの意図しない共有の防止をサポートします <br /><br />サンプル シナリオ: [Microsoft Teams のチャットやチャネル メッセージでの機密情報の保護](dlp-microsoft-teams.md) | [既定の DLP ポリシーの使用を開始する](get-started-with-the-default-dlp-policy.md)|
|[エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)| Windows 10 コンピューターで使用され共有されるアイテムに DLP 機能を拡張します | [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)|
