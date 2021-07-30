---
title: 前提条件&アクセス許可 - 脅威と脆弱性の管理
description: アプリケーションの使用を開始脅威と脆弱性の管理、関連する構成とアクセス許可を持っている必要があります。
keywords: 脅威& 脆弱性の管理アクセス許可の前提条件、脅威と脆弱性の管理アクセス許可の前提条件、Microsoft Defender for Endpoint TVM アクセス許可の前提条件、脆弱性の管理
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
ms.openlocfilehash: 9fde7ed4c7a3b621730e2b6cd73370d87ea9c92c
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651689"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>前提条件&アクセス許可 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

デバイスが次の条件を使用する必要があります。

- Microsoft Defender for Endpoint にオンボードされている

- サポート [されているオペレーティング システムとプラットフォームを実行する](tvm-supported-os.md)

- ネットワークに次の必須更新プログラムをインストールして展開し、脆弱性評価の検出率を向上させる必要があります。

  > リリース | セキュリティ更新プログラムの KB 番号とリンク
  > :---|:---
  > Windows 10バージョン 1709 | [KB4493441 および](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
  > Windows 10バージョン 1803 | [KB4493464](https://support.microsoft.com/help/4493464) および [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
  > Windows 10バージョン 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
  > Windows 10バージョン 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- ユーザーが検出した[脅威Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[修復Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)を支援するために、脅威と脆弱性の管理。 Configuration Manager を使用している場合は、本体を最新バージョンに更新します。

  > [!NOTE]
  > Intune 接続が有効になっている場合は、修復要求を作成するときに Intune セキュリティ タスクを作成するオプションを取得します。 接続が設定されていない場合、このオプションは表示されません。

- デバイス ページで表示できるセキュリティ推奨事項が 1 つ以上ある

- タグ付けまたは共同管理としてマークされている

## <a name="relevant-permission-options"></a>関連するアクセス許可オプション

1. セキュリティ管理者またはグローバルMicrosoft 365 Defender割り当てられたアカウントを使用して、ポータルにログインします。
2. ナビゲーション ウィンドウで、[エンドポイント] 設定 >**ロール>選択します**。

詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](user-roles.md)。

### <a name="view-data"></a>データを表示

- **セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する
- **脅威と脆弱性の管理**- ポータル脅威と脆弱性の管理データを表示する

### <a name="active-remediation-actions"></a>アクティブ修復アクション

- **セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理
- **脅威と脆弱性の管理 - 例外処理**- 新しい例外を作成し、アクティブな例外を管理する
- **脅威と脆弱性の管理 - 修復処理**- 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理

詳細については、「RBAC のアクセス許可 [オプション」を参照してください。](user-roles.md#permission-options)

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [サポート対象オペレーティング システムとプラットフォーム](tvm-supported-os.md)
- [デバイス値の割り当て](tvm-assign-device-value.md)
- [脅威と脆弱性の管理ダッシュボード](tvm-dashboard-insights.md)

