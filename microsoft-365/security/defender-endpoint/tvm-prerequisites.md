---
title: 権限&前提条件 - 脅威と脆弱性の管理
description: 脅威と脆弱性の管理の使用を開始する前に、関連する構成とアクセス許可を持っている必要があります。
keywords: 脅威&管理アクセス許可の前提条件、脅威と脆弱性管理のアクセス許可の前提条件、Microsoft Defender for Endpoint TVM アクセス許可の前提条件、脆弱性管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935187"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>権限&前提条件 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

デバイスが次の条件を使用する必要があります。

- Microsoft Defender for Endpoint にオンボードされている
- サポート [されているオペレーティング システムとプラットフォームを実行する](tvm-supported-os.md)
- ネットワークに次の必須更新プログラムをインストールして展開し、脆弱性評価の検出率を向上させる必要があります。

> Release | セキュリティ更新プログラムの KB 番号とリンク
> :---|:---
> Windows 10 Version 1709 | [KB4493441 および](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Version 1803 | [KB4493464](https://support.microsoft.com/help/4493464) および [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Version 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Version 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- 脅威と脆弱性管理によって検出された脅威を修復するために [、Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) および  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) にオンボードされます。 Configuration Manager を使用している場合は、本体を最新バージョンに更新します。
    - **注**: Intune 接続が有効になっている場合は、修復要求を作成するときに Intune セキュリティ タスクを作成するオプションを取得します。 接続が設定されていない場合、このオプションは表示されません。
- デバイス ページで表示できるセキュリティ推奨事項が 1 つ以上ある
- タグ付けまたは共同管理としてマークされている

## <a name="relevant-permission-options"></a>関連するアクセス許可オプション

1. セキュリティ管理者またはグローバル管理者の役割が割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。
2. ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。

詳細については、「役割ベースの [アクセス制御の役割の作成と管理」を参照してください。](user-roles.md)

### <a name="view-data"></a>データの表示

- **セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する
- **脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する

### <a name="active-remediation-actions"></a>アクティブな修復アクション

- **セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理
- **脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する
- **脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理

詳細については、「RBAC のアクセス許可 [オプション」を参照してください。](user-roles.md#permission-options)

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [サポート対象オペレーティング システムとプラットフォーム](tvm-supported-os.md)
- [デバイス値の割り当て](tvm-assign-device-value.md)
- [脅威と脆弱性の管理ダッシュボード](tvm-dashboard-insights.md)

