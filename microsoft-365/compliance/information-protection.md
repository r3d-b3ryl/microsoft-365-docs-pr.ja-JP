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
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259300"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 の Microsoft Information Protection

>*[Microsoft 365 セキュリティとコンプライアンスのライセンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft Information Protection (MIP) を実装すれば、機密情報がどこに保存されていても、どこに移動しても、それらの情報の検出、分類、保護が可能になります。

MIP 機能は Microsoft 365 コンプライアンスに含まれており、[データを把握](#know-your-data)し、[データを保護](#protect-your-data)し、[データの損失を防止する](#prevent-data-loss)ためのツールを提供しています。

![MIP が機密性の高いデータの検出、分類、保護にどのように役立つかについての画像](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="データを把握する":::

データの管理については、「[Microsoft 365 の Microsoft 情報ガバナンス](manage-Information-governance.md)」を参照してください。

## <a name="know-your-data"></a>データを把握する

> [!NOTE]
> Azure Purview でのデータの分類およびラベル付けの詳細については、現在プレビューですが、「[Azure Purviewにあるコンテンツに自動的にラベルを付ける](/azure/purview/create-sensitivity-label)」を参照し てください。
> 
> Azure Purview のリリースの発表については、次のブログ投稿を参照してください。「[Microsoft Information Protection および Microsoft Azure Purview: 相乗効果](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481)」および「[Spring Ignite 2021 での Azure Purview](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919)」。

データの状況を把握し、ハイブリッド環境全体にわたって重要なデータを識別するには、次の機能を使用します:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="データを把握する"::: 


|**機能**|**解決される問題**|**概要**|**ライセンス**|
|--|--|--|--|
|[機密情報の種類](sensitive-information-type-entity-definitions.md)| キーワード、信頼度レベル、近接度などの補強証拠とともに、組み込みの正規表現、カスタムの正規表現、関数を使用して、機密データを識別します。 機密情報の種類を使用して、組織内の特定の種類のデータを識別します。 既定の機密情報の種類を使用して、パスポート番号などの標準の種類のデータを検索します。 カスタム情報の種類を作成して、部品番号などの環境に固有の情報を識別します。 | [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)| |
|[トレーニング可能な分類子 (プレビュー)](classifier-learn-about.md)| 組み込みの分類子のいずれかを使用したり、独自のコンテンツを使用して分類子をトレーニングしたりして、データを分類することができます | [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-get-started-with.md)| |
|[データの分類](data-classification-overview.md) | 秘密度ラベルや保持ラベルが付けられているアイテムや、機密情報の種類として組織内で分類されているアイテムと、それらに対するユーザーのアクションを識別します  | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md)<br /><br /> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、視覚的なマーキングなどを含む柔軟な保護アクションを適用するには、次の機能を使用します。


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="データの保護":::

|**機能**|**解決される問題**|**概要**|**ライセンス**|
|--|--|--|--|
|[秘密度ラベル](sensitivity-labels.md)| 組織の内外を移動するデータをラベル付けして保護する、アプリ、サービス、デバイスにまたがる単一のソリューション <br /><br />サンプル シナリオ: [Power BI で秘密度ラベルを適用して表示し、エクスポート時にデータを保護する](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[秘密度ラベルの使用を開始する](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| クラウドのデータ ストア内にある機密情報の検出、ラベル付け、保護を行います。 | [クラウド内に保存されている規制対象データや機密データの検出、分類、ラベル付け、保護を行う](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Azure Information Protection 統合ラベル付けスキャナー](/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータ ストア内にある機密情報の検出、ラベル付け、保護 | [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[アクティビティ エクスプローラー]()||||


## <a name="transition-from-aip-to-mip"></a>AIP から MIP への切り替え
従来の Azure Information Protection の管理環境およびクライアントは、来年初めまでに廃止されます。 Microsoft Information Protection に移行することをお勧めします。移行するには、すべての既存のラベルとポリシーを移動する必要があります。 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="AIP から MIP への切り替え":::

## <a name="additional-capabilities"></a>追加機能
Microsoft 365 には、データを保護するための次の機能が含まれています:

|**機能**|**解決される問題**|**概要**|
|--|--|--|
| Office 365 Message Encryption (OME) | メール メッセージと添付ドキュメントはいずれのデバイス上のいずれのユーザーに送信される場合も暗号化されるため、承認された受信者のみがメールの情報を読むことができます。 <br /><br /> サンプル シナリオ: Advanced Message Encryption を使用して暗号化されたメールを無効にする | 新しい Message Encryption 機能を設定する |
| 二重キー暗号化 | どのような状況においても、保護されたコンテンツを復号化できるのは自分だけです。また規制要件により、地理的な境界内に暗号化キーを保持する必要があります | 二重キー暗号化の展開 |  
| カスタマー キーによるサービスの暗号化 | 承認されていないシステムや個人によるデータの閲覧を防止し、Microsoft データセンターの Bitlocker ディスク暗号化を補完します。 | Office 365 のカスタマー キーを設定する |
| SharePoint Information Rights Management (IRM) | これは、SharePoint リストとライブラリを保護するもので、ユーザーがドキュメントをチェックアウトした際に、ダウンロード済みのファイルを保護します。指定したポリシーに基づき、承認されているユーザーのみがファイルを閲覧したり使用したりできます。 | SharePoint 管理センターの Information Rights Management (IRM) の設定 |
| Rights Management コネクタ | Exchange または SharePoint Server およびファイル分類インフラストラクチャ (FCI) を使用する既存のオンプレミスの展開の保護のみが対象となっています。 | RMS コネクタの展開の手順 |



## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報が誤って過度に共有されてしまうのを防止するために、次の機能を使用します。

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="データの損失の防止":::

|**手順**|**説明**|**詳細情報**|
|--|--|--|
|[DLP ポリシーの設計](data-loss-prevention-policies.md)| 識別情報 (機密情報の種類、ラベルなど) のモードのプランを作成する <br /><br /> ポリシーのターゲット (サービス、クライアント、サード パーティ アプリ) のプランを作成する <br /><br /> ポリシー ヒントなどのプランを作成する||
||||




|**機能**|**解決される問題**|**概要**|
|--|--|--|
|[データ損失防止について](dlp-learn-about-dlp.md)| 機密アイテムの意図しない共有の防止をサポートします。 | [既定の DLP ポリシーの使用を開始する](get-started-with-the-default-dlp-policy.md)|
|[エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)| Windows 10 コンピューターで使用され共有されるアイテムに DLP 機能を拡張します。 | [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md)|
|[Microsoft Compliance Extension (プレビュー) の詳細情報](dlp-chrome-learn-about.md) | Chrome ブラウザーに DLP 機能を拡張します | [Microsoft Compliance Extension (プレビュー) を開始する](dlp-chrome-get-started.md)|
|[Microsoft 365 のデータ損失防止のオンプレミス スキャナーについての詳細情報 (プレビュー)](dlp-on-premises-scanner-learn.md)|ファイル アクティビティの DLP 監視とそれらのファイルの保護アクションを、オンプレミスのファイル共有と SharePoint フォルダーおよびドキュメント ライブラリに拡張します。|[Microsoft 365 のデータ損失防止のオンプレミス スキャナー (プレビュー) の使用を開始する](dlp-on-premises-scanner-get-started.md)|
|[Microsoft Teams のチャットやチャネル メッセージでの機密情報の保護](dlp-microsoft-teams.md) | 一部の DLP 機能を Teams のチャットおよびチャネル メッセージに拡張します | [Microsoft Teams の既定のデータ損失防止ポリシーについての詳細情報 (プレビュー)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>その他のリソース

多くの組織は、これらの情報保護機能を使用して、データ プライバシー規制に準拠しています。 これを支援するために、安全なアクセス、脅威からの保護、情報からの保護、データ ガバナンスなど、Microsoft 36 5全体の機能を計画および実装するためのエンドツーエンドのプロセスをガイドするワークフローを設計しました。 詳細については、「[Microsoft 365を使用したデータプライバシー規制の情報保護の展開 (aka.ms/m365dataprivacy)](../solutions/information-protection-deploy.md)」を参照してください。 

さらに、情報保護機能を実装するための統合戦略を計画するのに役立てるため、*Microsoft 365 の情報保護およびコンプライアンス機能の図のセット* をダウンロードしてください。  これらのイラストを自分の用途に合わせて自由にアレンジしてください。

| アイテム | 説明 |
|:-----|:------------|
|[![モデル ポスター: Microsoft 365 の情報保護とコンプライアンスの機能](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [PDF としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日本語: [PDF としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Visio としてダウンロードする](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 更新日: 2020 年 10 月|含まれる内容: <ul><li>  Microsoft の情報保護およびデータ損失防止</li><li>アイテム保持ポリシーと保持ラベル </li><li>情報バリア</li><li>コミュニケーション コンプライアンス</li><li>インサイダー リスクの管理</li><li>サードパーティのデータの取り込み</li>|

