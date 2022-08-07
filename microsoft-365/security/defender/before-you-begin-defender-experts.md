---
title: Microsoft Defender Experts for Hunting サービスに登録する前の主要なインフラストラクチャ要件
ms.reviewer: ''
description: このセクションでは、満たす必要がある主要なインフラストラクチャ要件と、データ アクセスとコンプライアンスに関する重要な情報について説明します
keywords: マネージド脅威ハンティング サービス、マネージド 脅威ハンティング、マネージド検出と応答 (MDR) サービス、MTE、Microsoft 脅威エキスパート、MTE-TAN、DEFENDER エキスパート通知、ターゲット攻撃通知、Microsoft Defender エキスパートの捜索、脅威の捜索と分析。
search.product: Windows 10
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 51e882c879f9365fbdc5b4a70d2ade106d061d51
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276222"
---
# <a name="before-you-begin-using-defender-experts-for-hunting"></a>Defender Experts for Hunting の使用を開始する前に

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

このドキュメントでは、Microsoft Defender エキスパート for Hunting サービスに登録する前に、満たす必要がある主要なインフラストラクチャ要件と、データ アクセスとコンプライアンスに関する重要な情報について説明します。 Microsoft は、マネージド サービスを使用するお客様が、最も価値のある資産であるデータを弊社に委託することを理解しています。

## <a name="check-if-your-environment-meets-licensing-and-access-prerequisites"></a>環境がライセンスとアクセスの前提条件を満たしているかどうかを確認する

Microsoft Defender Experts for Hunting は、既存の Defender 製品とは別のサービスです。 このサービスに登録する前に、必要なライセンスとアクセス権があることを確認してください。 

### <a name="eligibility-and-licensing"></a>資格とライセンス

Defender Experts for Hunting のお客様には、毎月最初に 2 つのエキスパート オンデマンド クレジットが割り当てられます。これは、質問の送信に使用される場合があります。 未使用のクレジットの有効期限は、割り当て日から 90 日間、またはサブスクリプション期間の終了時のいずれか短い方です。

Microsoft の商用ライセンス条項の詳細については、 [このページ](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA)を参照してください。

### <a name="access-requirements"></a>アクセス要件

組織のだれでも、Microsoft Defender Experts for Hunting サービスの顧客の関心フォームを完了できますが、コマーシャル エグゼクティブと協力して SKU を処理する必要があります。 サービス機能に完全にアクセスするには、特定のロールとアクセス許可が必要な場合があります。 詳細については、[Microsoft 365 Defenderのロールベースのアクセス制御のカスタム ロール](custom-roles.md)を参照してください。

## <a name="understand-the-services-availability-and-data-access-requirements"></a>サービスの可用性とデータ アクセスの要件を理解する

Defender Experts for Hunting は、エンドポイント、電子メール、ID、クラウド アプリ全体で脅威をプロアクティブに検出するマネージド脅威ハンティング サービスです。 お客様に代わって捜索を実行するには、Microsoft の専門家がMicrosoft 365 Defender高度なハンティング データにアクセスする必要があります。 このサービスに登録すると、そのデータにアクセスするためのアクセス許可が Microsoft エキスパートに付与されます。

次のセクションでは、サービスのデータ使用量、コンプライアンス、可用性に関する追加情報を列挙します。 データの評価と保護に関する Microsoft のコミットメントの詳細については、 [セキュリティ センター](https://aka.ms/trustcenter-dex4hunting) の>、 **その他の製品とサービス** > **のマネージド セキュリティ サービス** > [**Microsoft Defender Expert for Hunting**](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE51fRH) までスクロールダウンしてください。

### <a name="data-collection-usage-and-retention"></a>データの収集、使用状況、および保持

既存の Defender サービスからの捜索に使用されるすべてのデータは、引き続き顧客の元のMicrosoft 365 Defenderサービスの保存場所に存在します。 [詳細情報](../../enterprise/o365-data-locations.md)

ケース チケットやアナリスト ノートなどの Defender Experts for Hunting 運用データは、Microsoft 365 Defenderサービスの保存場所に関係なく、サービスの長さのために米国リージョンの Microsoft データ センターに生成および保存されます。 レポート ダッシュボード用に生成されたデータは、顧客のMicrosoft 365 Defenderサービスの保存場所に格納されます。 レポート データと運用データは、顧客がサービスを離れた後、90 日以内の猶予期間保持されます。

Microsoft の専門家は、[高度なハンティング テーブルMicrosoft 365 Defender高度なハンティング ログ](../../security/defender/advanced-hunting-schema-tables.md)を検索します。 これらのテーブルのデータは、顧客が有効になっている Defender サービスのセットによって異なります (たとえば、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps、Azure Active Directory)。 専門家は、大規模な一連の内部脅威インテリジェンス データを使用して、捜索と自動化を通知します。

### <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Defender Experts for Hunting を購入してオンボードすると、高度なハンティング データにアクセスするためのアクセス許可が Microsoft エキスパートに付与されます。

このサービスは、既存のセキュリティとプライバシーの標準に沿って開発されており、ISO 27001 や ISO 27018 など、いくつかの認定に向けて取り組んでいます。

### <a name="availability"></a>Availability

このサービスは、商用パブリック クラウドのお客様向けに世界中で利用できます。 現在、政府機関およびソブリン クラウドのお客様は利用できません。

### <a name="languages"></a>言語

このサービスは現在、英語でのみ提供されています。

## <a name="apply-for-microsoft-defender-experts-for-hunting-service"></a>ハンティング サービスの Microsoft Defender エキスパートに申し込む

まだ行っていない場合は、Defender Experts for Hunting の顧客の関心フォームに入力できます。

1. [顧客の関心フォームに入力します](https://aka.ms/DEX4HuntingCustomerInterestForm)。 会社の誰でも申請できますが、承諾された場合は、コマーシャル エグゼクティブと協力して SKU を処理する必要があります。
2. 名前、会社名、会社の電子メール ID を入力します。
3. **[送信]** を選択します。 営業チームの誰かが 5 営業日以内に連絡を取ります。


### <a name="next-step"></a>次のステップ

- [Defender Experts for Hunting の使用を開始する](onboarding-defender-experts-for-hunting.md)
