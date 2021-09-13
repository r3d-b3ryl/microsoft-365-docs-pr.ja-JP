---
title: Windows における情報保護の概要
ms.reviewer: ''
description: 機密情報の特定と保護を行うWindows保護の仕組みについて説明します。
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
ms.openlocfilehash: b3fa8c7c919edc438bb63fe4baaeca6711a3a045
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212264"
---
# <a name="information-protection-in-windows-overview"></a>Windows における情報保護の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

情報保護は、Microsoft 365 Enterpriseの生産性を可能にしながら、機密データを安全に保つインテリジェントな保護を提供する、Microsoft 365 Enterpriseスイートの不可欠な部分です。

> [!TIP]
> Microsoft Defender for Endpoint と Microsoft Information Protectionデバイス上の機密データを検出、保護、監視する方法に関するブログ記事を[Windowsしてください](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。

Defender for Endpoint は、データの検出、分類、および保護に次のメソッドを適用します。

- **データ検出**- 危険にさらされているデバイスWindowsデータを特定する
- **データの分類**- コンプライアンス センターで管理される共通Microsoft Information Protection (MIP) ポリシーに基Office 365データ&分類します。 自動分類を使用すると、エンド ユーザーが手動で分類していなくても、機密データを保護できます。

## <a name="data-discovery-and-data-classification"></a>データ検出とデータ分類

Defender for Endpoint は、機密ラベルを持つファイルと機密情報の種類を含むファイルを自動的に検出します。

機密ラベルは機密コンテンツを分類し、保護するのに役立ちます。

データ損失防止 (DLP) Office 365の機密情報の種類は、次の 2 つのカテゴリに分類されます。

- 既定値
- Custom

既定の機密情報の種類には、銀行口座番号、社会保障番号、国内の ID などの情報が含まれます。 詳細については、「機密情報の [種類の検索方法」を参照してください](/office365/securitycompliance/what-the-sensitive-information-types-look-for)。

カスタム型は、ユーザーが定義する種類であり、異なる種類の機密情報 (従業員の ID やプロジェクト番号など) を保護するように設計されています。 詳細については、「カスタム機密情報の [種類を作成する」を参照してください](/office365/securitycompliance/create-a-custom-sensitive-information-type)。

デバイス上でファイルが作成または編集Windows Defender for Endpoint はコンテンツをスキャンして、機密情報が含まれているか評価します。

ラベルまたは情報の種類を使用して Defender for Endpoint によって機密情報を含むファイルが検出された場合、デバイスから Azure Information Protection に自動的に転送するように、Azure Information Protection 統合を有効にします。

![Azure Information Protection を使用した設定ページのイメージ。](images/atp-settings-aip.png)

報告された信号は、Azure Information Protection - データ検出ダッシュボードで表示できます。

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection - データ検出ダッシュボード

このダッシュボードには、Defender for Endpoint と Azure Information Protection の両方によって検出されたデータの要約された検出情報が表示されます。 Defender for Endpoint のデータは、場所の種類 - エンドポイントでマークされます。

![Azure Information Protection のイメージ - データ検出。](images/azure-data-discovery.png)

右側の [デバイス リスク] 列に注意してください。このデバイス リスクは Defender for Endpoint から直接派生し、Defender for Endpoint によって検出されたアクティブなセキュリティ脅威に基づいて、ファイルが検出されたセキュリティ デバイスのリスク レベルを示します。

デバイスをクリックすると、このデバイスで観察されたファイルの一覧が表示され、そのデバイスの感度ラベルと情報の種類が表示されます。

> [!NOTE]
> Azure Information Protection Dashboard Discovery が検出されたファイルを反映するには、約 15 ~ 20 分かかります。

## <a name="log-analytics"></a>Log Analytics

Defender for Endpoint に基づくデータ検出は [Azure Log Analytics](/azure/log-analytics/log-analytics-overview)でも利用できます。ここで、生データに対して複雑なクエリを実行できます。

Azure Information Protection analytics の詳細については、「Azure Information Protection の中央 [レポート」を参照してください](/azure/information-protection/reports-aip)。

Azure portal で Azure Log Analytics を開き、クエリ ビルダー (標準またはクラシック) を開きます。

Defender for Endpoint データを表示するには、次のクエリを実行します。

```text
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

### <a name="prerequisites"></a>前提条件

- お客様は Azure Information Protection のサブスクリプションを持っている必要があります。
- Azure Information Protection の統合を次のMicrosoft Defender セキュリティ センター。
  - [詳細]**設定** に移動Microsoft Defender セキュリティ センター、[全般] の [**詳細設定] 設定** を **クリックします**。
