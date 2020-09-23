---
title: ロシアの個人データローカライズ要件
description: 個人データ、ロシア市民の個人データ記録、systematization、蓄積、保存、明確化、および抽出が、ロシアにある Microsoft サービスおよびデータベースで実行される方法について説明します。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 29c56d525375162926d34bd298bbbd660964438d
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208159"
---
# <a name="russian-personal-data-localization-requirements"></a>ロシアの個人データローカライズ要件

2015年9月1日時点で、個人データオペレーターと見なされる組織では、個人データを収集する際に、ロシア市民の個人データ記録、systematization、蓄積、保存、説明 (更新、変更)、および抽出がロシアにあるデータベース (「個人データのローカリゼーション要件」) によって実行されることを保証する必要があります。<sup>1</sup>

Microsoft Azure、Microsoft 365、Dynamics 365、および Power Platform などの個人データ処理を有効にすることを含む、組織で利用可能な microsoft Online Services (教育機関に限定されない) (hereinafter と呼ばれる) (詳細については、「 [Microsoft Trust Center](https://www.microsoft.com/trust-center)」を参照してください)。

ユーザー情報システムによって処理された情報の種類と内容に基づいて、Microsoft クラウド製品を使用しているものも含めて、個人データ情報システム (' PDIS ', ' ISPD ') と見なされる場合があります。 お客様が PDM として認定されているシステムで Microsoft Online Services を使用することを希望している場合は、Microsoft は、お客様に対して、次に示すその他のソリューションを検討することをお勧めします。 提供されているすべてのシナリオは、標準のビジネス製品に対する追加オプションとして、お客様が利用できます。

このお客様には、PDIS 個人データ事業者がコンプライアンスを担当しており、個人データローカリゼーションの適用可能な法的要件を分析して評価する必要があることに注意してください。また、独自の判断で、PDIS の個人データの処理がロシアの個人データの法則に準拠していることを確認するために十分な<sup>2</sup>

## <a name="subscribing-to-microsoft-online-services"></a>Microsoft Online Services を購読する

### <a name="microsoft-id-management"></a>Microsoft ID の管理

Microsoft は、microsoft のクラウドソリューションプロバイダー (CSP) パートナー経由で microsoft Online Services (Microsoft Azure、Microsoft 365、Dynamics 365、および電源プラットフォーム) へのサブスクライブを検討することをお客様に招待しています。 詳細については、 [CSP パートナーの一覧](https://pinpoint.microsoft.com/search?type=services&campaign=691) を参照してください。

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a>Microsoft Online Services のユーザー Id とアクセス権を管理する

Microsoft Azure、Microsoft 365、Dynamics 365、電源プラットフォームなどの Microsoft Online Services の場合、ユーザーの確認とアクセスの管理は [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/)を介して実行されます。 Microsoft のお客様が Microsoft クラウドサービス (Windows Server Active Directory (AD) やその他の ID 管理システムなど) に対してローカルの id 管理システムを使用している場合、お客様は Azure AD Connect を通じてこのようなシステムを Azure Active Directory (AAD) にすばやく統合することができます。 詳細については、「 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) 」オプションを参照してください。 また、Microsoft のお客様は、サードパーティベンダーのアプリケーションやソリューションを使用してユーザーを管理し、そのローカル識別システムを Azure AD と統合することを検討することもできます。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Microsoft コンプライアンスマネージャーを使用してリスクを評価する

[Microsoft コンプライアンスマネージャー](compliance-manager.md) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能であり、組織のコンプライアンスの状況を理解し、リスクを軽減するためのアクションを実行するのに役立ちます。 コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアムテンプレートが用意されています。 [コンプライアンスマネージャー] の [ **評価テンプレート** ] ページでテンプレートを検索します。 [コンプライアンスマネージャーで評価を作成](compliance-manager-assessments.md)する方法について説明します。

## <a name="questions-and-support"></a>質問とサポート

技術的および請求に関する質問については、以下の Microsoft サポートリソースを参照してください。 その他の質問や説明については、Microsoft の [プライバシーチーム](https://support.microsoft.com/gp/privacy-page)にお問い合わせください。

### <a name="microsoft-azure"></a>Microsoft Azure

- **Web サイト**: [Microsoft Azure サポート](https://aka.ms/GetAzureSupport)
- **無料電話**番号: 8 800 200 8001
- **ローカル通話**: 495 916 7171
- **オンラインサポート**: [Azure ポータル](https://portal.azure.com)経由でクエリを送信する

### <a name="microsoft-365"></a>Microsoft 365

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**:[管理センター](https://portal.office.com/)からクエリを送信する

### <a name="dynamics-365"></a>Dynamics 365

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**: [Dynamics サポートポータル](https://dynamics.microsoft.com/support/)でクエリを送信する

### <a name="power-platform"></a>電源プラットフォーム

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**:[電源プラットフォームサポート](https://docs.microsoft.com/power-platform/admin/get-help-support)経由でクエリを送信する

> [!NOTE]
> <sup>1</sup> 連邦法はありません。 242-FZ (edition 12.31.2014) ' は、ロシアのフェデレーションの特定の法律上の行動に対して、個人データの処理手順を明確にするための情報および電気通信ネットワークの07.21.2014 <br>
> <sup>2</sup> 連邦法はありません。 07.27 の場合、個人データの 152-FZ。 2006<br>
