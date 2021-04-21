---
title: Windows における情報保護の概要
ms.reviewer: ''
description: 機密情報を特定して保護するために Windows で情報保護がどのように機能するのかについて説明します。
keywords: 情報、保護、dlp、データ、損失、防止、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 803c0af0c495eedfd26023d4e71d98df6a1b1b64
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904024"
---
# <a name="information-protection-in-windows-overview"></a>Windows における情報保護の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

情報保護は、Microsoft 365 Enterprise スイートの不可欠な部分で、機密性の高いデータを安全に保ちながら、職場での生産性を実現するためのインテリジェントな保護を提供します。


>[!TIP]
> Microsoft Defender for Endpoint (以前は Microsoft Defender ATP) が Microsoft Information Protection と統合して Windows デバイス上の機密データを検出、保護、監視する方法に関するブログ記事をお [読みください](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。

Defender for Endpoint は、データの検出、分類、および保護に次のメソッドを適用します。

- **データ検出** - 危険にさらされている Windows デバイス上の機密データを特定する
- **データの分類** - コンプライアンス センターで管理される一般的な Microsoft Information Protection (MIP) ポリシーに基づいてデータOffice自動的&分類します。 自動分類を使用すると、エンド ユーザーが手動で分類していなくても、機密データを保護できます。


## <a name="data-discovery-and-data-classification"></a>データ検出とデータ分類

Defender for Endpoint は、機密ラベルを持つファイルと機密情報の種類を含むファイルを自動的に検出します。

機密ラベルは機密コンテンツを分類し、保護するのに役立ちます。

365 データ損失防止 (DLP) Office実装の機密情報の種類は、次の 2 つのカテゴリに分類されます。

- 既定値
- Custom

既定の機密情報の種類には、銀行口座番号、社会保障番号、国内の ID などの情報が含まれます。 詳細については、「機密情報の [種類の検索方法」を参照してください](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)。

カスタム型は、ユーザーが定義する種類であり、異なる種類の機密情報 (従業員の ID やプロジェクト番号など) を保護するように設計されています。 詳細については、「カスタム機密情報の [種類を作成する」を参照してください](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)。

Windows デバイスでファイルが作成または編集されると、Defender for Endpoint はコンテンツをスキャンして、機密情報が含まれているか評価します。

ラベルまたは情報の種類を使用して Defender for Endpoint によって機密情報を含むファイルが検出された場合、デバイスから Azure Information Protection に自動的に転送するように、Azure Information Protection 統合を有効にします。

![Azure Information Protection を使用した設定ページのイメージ](images/atp-settings-aip.png)

報告された信号は、Azure Information Protection - データ検出ダッシュボードで表示できます。

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection - データ検出ダッシュボード

このダッシュボードには、Defender for Endpoint と Azure Information Protection の両方によって検出されたデータの要約された検出情報が表示されます。 Defender for Endpoint のデータは、場所の種類 - エンドポイントでマークされます。

![Azure Information Protection のイメージ - データ検出](images/azure-data-discovery.png)

右側の [デバイス リスク] 列に注意してください。このデバイス リスクは Defender for Endpoint から直接派生し、Defender for Endpoint によって検出されたアクティブなセキュリティ脅威に基づいて、ファイルが検出されたセキュリティ デバイスのリスク レベルを示します。

デバイスをクリックすると、このデバイスで観察されたファイルの一覧が表示され、そのデバイスの感度ラベルと情報の種類が表示されます。

>[!NOTE]
>Azure Information Protection Dashboard Discovery が検出されたファイルを反映するには、約 15 ~ 20 分かかります。

## <a name="log-analytics"></a>Log Analytics

Defender for Endpoint に基づくデータ検出は [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)でも利用できます。ここで、生データに対して複雑なクエリを実行できます。

Azure Information Protection analytics の詳細については、「Azure Information Protection の中央 [レポート」を参照してください](https://docs.microsoft.com/azure/information-protection/reports-aip)。

Azure portal で Azure Log Analytics を開き、クエリ ビルダー (標準またはクラシック) を開きます。

Defender for Endpoint データを表示するには、次のクエリを実行します。

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**前提条件:**

- お客様は Azure Information Protection のサブスクリプションを持っている必要があります。
- Microsoft Defender セキュリティ センターで Azure Information Protection の統合を有効にする:
    - [Microsoft Defender **セキュリティ センターの** 設定] に移動し、[全般] の [**詳細設定] を****クリックします**。



