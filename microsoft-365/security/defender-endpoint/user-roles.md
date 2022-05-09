---
title: ロールベースのアクセス制御のロールを作成および管理する
description: ロールを作成し、ロールベースのアクセス制御の実装の一部としてロールに割り当てられたアクセス許可を定義Microsoft 365 Defender
keywords: ユーザー ロール、ロール、アクセス RBAC
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6f853df2d37cc41b2effb55ff10418af67df2bd6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324075"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>ロールベースのアクセス制御のロールを作成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>ロールを作成し、Azure Active Directory グループにロールを割り当てる

次の手順では、Microsoft 365 Defenderでロールを作成する方法について説明します。 ユーザー グループAzure Active Directory既に作成済みであることを前提としています。

1. セキュリティ管理者または<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">グローバル管理者</a>ロールが割り当てられているアカウントを使用してMicrosoft 365 Defenderにログインします。

2. ナビゲーション ウィンドウで、(**[アクセス許可**] **で) 設定** \> **エンドポイント** \> **ロール** を選択します。

3. [ **項目の追加]** を選択します。

4. ロールに割り当てるロール名、説明、アクセス許可を入力します。

5. [**次へ**] を選択して、Azure AD セキュリティ グループにロールを割り当てます。

6. フィルターを使用して、このロールに追加するAzure AD グループを選択します。

7. **保存して閉じます**。

8. 構成設定を適用します。

> [!IMPORTANT]
> ロールを作成したら、デバイス グループを作成し、作成したロールに割り当てることでデバイス グループへのアクセス権を提供する必要があります。

### <a name="permission-options"></a>アクセス許可オプション

- **データを表示**
  - **セキュリティ操作** - ポータル内のすべてのセキュリティ操作データを表示する
  - **脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する

- **アクティブ修復アクション**
  - **セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理
  - **脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する
  - **脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理

- **アラートの調査** - アラートの管理、自動調査の開始、スキャンの実行、調査パッケージの収集、デバイス タグの管理、およびポータブル実行可能ファイル (PE) ファイルのみのダウンロード

- **ポータル システム設定の管理** - ストレージ設定、SIEM、脅威の Intel API 設定 (グローバルに適用)、詳細設定、自動ファイル アップロード、ロール、デバイス グループを構成する

    > [!NOTE]
    > この設定は、Microsoft Defender for Endpoint管理者 (既定) ロールでのみ使用できます。

- **Security Center でセキュリティ設定を管理** する - アラート抑制設定の構成、自動化のフォルダー除外の管理、オンボードデバイスとオフボード デバイス、電子メール通知の管理、評価ラボの管理

- **ライブ応答機能**
  - **基本的な** コマンド:
    - ライブ応答セッションを開始する
    - リモート デバイスで読み取り専用のライブ応答コマンドを実行する (ファイルのコピーと実行を除く)
    - ライブ応答を使用してリモート デバイスからファイルをダウンロードする
  - **高度な** コマンド:
    - ファイル ページから PE ファイルと非 PE ファイルをダウンロードする
    - リモート デバイスにファイルをアップロードする
    - ファイル ライブラリからスクリプトを表示する
    - ファイル ライブラリからリモート デバイスでスクリプトを実行する

使用可能なコマンドの詳細については、「 [ライブ応答を使用してデバイスを調査する](live-response.md)」を参照してください。

## <a name="edit-roles"></a>ロールを編集する

1. セキュリティ管理者または<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">グローバル管理者</a>ロールが割り当てられているアカウントを使用してMicrosoft 365 Defenderにログインします。

2. ナビゲーション ウィンドウで、(**[アクセス許可**] **で) 設定** \> **エンドポイント** \> **ロール** を選択します。

3. 編集するロールを選択します。

4. **[編集]** をクリックします。

5. ロールに割り当てられている詳細またはグループを変更します。

6. [ **保存] をクリックして閉じます**。

## <a name="delete-roles"></a>ロールを削除する

1. セキュリティ管理者または<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">グローバル管理者</a>ロールが割り当てられているアカウントを使用してMicrosoft 365 Defenderにログインします。

2. ナビゲーション ウィンドウで、(**[アクセス許可**] **で) 設定** \> **エンドポイント** \> **ロール** を選択します。

3. 削除するロールを選択します。

4. ドロップダウン ボタンをクリックし、[ロールの **削除**] を選択します。

## <a name="related-topic"></a>関連トピック

- [ポータルにアクセスするためのユーザーの基本的なアクセス許可](basic-permissions.md)
- [デバイス グループの作成と管理](machine-groups.md)
