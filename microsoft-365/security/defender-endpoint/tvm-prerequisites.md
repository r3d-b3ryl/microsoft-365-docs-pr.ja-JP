---
title: アクセス許可&前提条件 - 脅威と脆弱性の管理
description: 脅威と脆弱性の管理の使用を開始する前に、関連する構成とアクセス許可があることを確認します。
keywords: 脅威& 脆弱性の管理アクセス許可の前提条件、脅威と脆弱性の管理アクセス許可の前提条件、Microsoft Defender for Endpoint TVM アクセス許可の前提条件、脆弱性の管理
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 343a5fd1033a6d954c7cd62e2558a4b401f69b20
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165548"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>アクセス許可&前提条件 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

デバイスが次の点を確認します。

- Microsoft Defender for Endpointにオンボードされている

- [サポートされているオペレーティング システムとプラットフォームを実行する](tvm-supported-os.md)

- ネットワークに次の必須の更新プログラムをインストールしてデプロイし、脆弱性評価の検出率を高めます。

  > Release | セキュリティ更新プログラムの KB 番号とリンク
  > :---|:---
  > Windows 10 バージョン 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) と [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
  > Windows 10 バージョン 1803 | [KB4493464](https://support.microsoft.com/help/4493464) および [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
  > Windows 10 バージョン 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
  > Windows 10 バージョン 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)とMicrosoft Endpoint Configuration Managerにオンボードされ、[脅威と脆弱性の管理](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)によって検出された脅威の修復に役立ちます。 Configuration Managerを使用している場合は、本体を最新バージョンに更新します。

  > [!NOTE]
  > Intune接続が有効になっている場合は、修復要求を作成するときにIntuneセキュリティ タスクを作成するオプションが表示されます。 接続が設定されていない場合、このオプションは表示されません。

- デバイス ページで表示できるセキュリティに関する推奨事項を少なくとも 1 つ持っている

- 共同管理としてタグ付けまたはマークされている

## <a name="relevant-permission-options"></a>関連するアクセス許可オプション

1. セキュリティ管理者またはグローバル管理者ロールが割り当てられているアカウントを使用して、Microsoft 365 Defender ポータルにログインします。
2. ナビゲーション ウィンドウで、[**エンドポイント>ロール設定 >**] を選択します。

詳細については、「[ロールベースのアクセス制御のロールの作成と管理](user-roles.md)」を参照してください。

### <a name="view-data"></a>データを表示

- **セキュリティ操作** - ポータル内のすべてのセキュリティ操作データを表示する
- **脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する

### <a name="active-remediation-actions"></a>アクティブ修復アクション

- **セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理
- **脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する
- **脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理

詳細については、「[RBAC アクセス許可オプション」を](user-roles.md#permission-options)参照してください。

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [サポート対象オペレーティング システムとプラットフォーム](tvm-supported-os.md)
- [デバイス値の割り当て](tvm-assign-device-value.md)
- [脅威と脆弱性の管理ダッシュボード](tvm-dashboard-insights.md)

