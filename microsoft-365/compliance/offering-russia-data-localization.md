---
title: ロシアの個人データローカライズ要件
description: 個人データ、ロシア市民の個人データ記録、systematization、蓄積、保存、明確化、および抽出が、ロシアにある Microsoft サービスおよびデータベースで実行される方法について説明します。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: 70e36d4f11f7fc1a5870f41a32351cf7078bdc68
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065772"
---
# <a name="russian-personal-data-localization-requirements"></a>ロシアの個人データローカライズ要件

2015年9月1日時点では、個人データオペレーターと見なされ、個人データを収集するときには、ロシア市民の個人データの記録、systematization、蓄積、ストレージ、説明 (更新、変更)、および抽出がロシアにあるデータベース (「個人データのローカリゼーション要件」) によって実行されます。<sup>1</sup>

Microsoft Online Services (教育機関に限定されているが、教育機関に限定されるものではありません) (hereinafter とも呼ばれます)。個人データ処理 (Microsoft Azure、Microsoft 365、Dynamics 365、電源プラットフォームなど) が、ロシア外のデータ処理センターから提供されます (詳細については、「 [Microsoft Trust Center」](https://www.microsoft.com/trust-center)を参照

ユーザー情報システムによって処理された情報の種類と内容に基づいて、たとえば、Microsoft クラウド製品を使用しているものも含め、個人データ情報システム (' PDIS ', ' ISPD ') と見なされることがあります。 お客様が、Microsoft Online Services をシステムで使用することを希望している場合は、そのアーキテクチャおよび処理される情報の種類を通じて、そのお客様に対して、次に示す使用可能なソリューションを検討することをお勧めします。 以下に示すすべてのシナリオは、標準のビジネスサービスに対する追加オプションとして、お客様に提供されています。

このお客様には、pdis 個人データオペレーターが、コンプライアンスを担当しており、個人データのローカライズに関する適用可能な法的要件を分析して評価する必要があります。また、独自の判断で、PDIS の個人データの処理がロシアの個人データの法則に準拠していることを確認してください。<sup>2</sup>

## <a name="subscribing-to-microsoft-online-services"></a>Microsoft Online Services を購読する

### <a name="microsoft-id-management"></a>Microsoft ID の管理

Microsoft は、microsoft のクラウドソリューションプロバイダー (CSP) パートナー経由で Microsoft Online Services-Microsoft Azure、microsoft 365、Dynamics 365、および電源プラットフォームへのサブスクライブを検討することをお客様に招待しています。 詳細については、 [CSP パートナーの一覧](https://pinpoint.microsoft.com/search?type=services&campaign=691)を参照してください。

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a>Microsoft Online Services のユーザー Id とアクセス権を管理する

Microsoft Azure などの Microsoft Online Services の場合、Microsoft 365、Dynamics 365、およびパワープラットフォームユーザーの確認とアクセス管理は、 [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/)によって実行されます。 Microsoft のお客様が Microsoft クラウドサービス (Windows Server Active Directory (AD) やその他の ID 管理システムなど) に対してローカルの id 管理システムを使用している場合、お客様は Azure AD Connect を通じてこのようなシステムを Azure Active Directory (AAD) にすばやく統合することができます。 詳細については、「 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) 」オプションを参照してください。 また、Microsoft のお客様は、サードパーティベンダーのアプリケーションとソリューションを使用してユーザーを管理し、そのローカル識別システムを Azure AD と統合することを検討することもできます。

## <a name="questions-and-support"></a>質問とサポート

技術的および請求に関する質問については、以下の Microsoft サポートリソースを参照してください。 詳細な質問や説明については、Microsoft の[プライバシーチーム](https://support.microsoft.com/gp/privacy-page)にお問い合わせください。

### <a name="microsoft-azure"></a>Microsoft Azure

- **Web サイト**: [Microsoft Azure サポート](https://aka.ms/GetAzureSupport)
- **無料電話**番号: 8 800 200 8001
- **ローカル通話**: 495 916 7171
- **オンラインサポート**: [Azure Portal](https://portal.azure.com)を使用してクエリを送信する

### <a name="microsoft-365"></a>Microsoft 365

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**:[管理センター](https://portal.office.com/)からクエリを送信する

### <a name="dynamics-365"></a>Dynamics 365

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**: [Dynamics support ポータル](https://dynamics.microsoft.com/support/)を使用してクエリを送信する

### <a name="power-platform"></a>電源プラットフォーム

- **無料電話**番号: 8 10 800 2548 1044
- **ローカル通話**: 499 922 8623
- **オンラインサポート**:[パワープラットフォームサポート](https://docs.microsoft.com/power-platform/admin/get-help-support)によるクエリの送信

> [!NOTE]
> <sup>1</sup>連邦法はありません。 242-FZ (edition 12.31.2014) ' は、ロシアのフェデレーションの特定の法律上の行動に対して、個人データの処理手順を明確にするための情報および電気通信ネットワークの07.21.2014 <br>
> <sup>2</sup>連邦法はありません。 07.27 の場合、個人データの 152-FZ。 2006<br>
