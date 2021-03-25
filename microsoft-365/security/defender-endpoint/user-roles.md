---
title: 役割ベースのアクセス制御の役割を作成および管理する
description: 役割を作成し、役割に割り当てられたアクセス許可を Microsoft Defender セキュリティ センターの役割ベースのアクセス制御実装の一部として定義する
keywords: ユーザー の役割、役割、アクセスの rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065948"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>役割ベースのアクセス制御の役割を作成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>役割を作成し、役割を Azure Active Directory グループに割り当てる

次の手順では、Microsoft Defender セキュリティ センターで役割を作成する方法について説明します。 Azure Active Directory ユーザー グループが既に作成済みである必要があります。

1. セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。

2. ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。

3. [アイテム **の追加] を選択します**。

4. 役割に割り当てる役割名、説明、およびアクセス許可を入力します。

5. [ **次へ]** を選択して、役割を Azure セキュリティ AD割り当てる。

6. このロールに追加する Azure ADグループをフィルターを使用して選択します。

7. **保存して閉じます**。

8. 構成設定を適用します。

> [!IMPORTANT]
> 役割を作成したら、デバイス グループを作成し、作成した役割に割り当て、デバイス グループにアクセス権を提供する必要があります。

### <a name="permission-options"></a>アクセス許可オプション

- **データの表示**
    - **セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する
    - **脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する

- **アクティブな修復アクション**
    - **セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理
    - **脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する
    - **脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理

- **アラートの調査** - アラートの管理、自動調査の開始、スキャンの実行、調査パッケージの収集、デバイス タグの管理、ポータブル実行可能ファイル (PE) ファイルのダウンロードのみ 

- **ポータル システム設定の管理** - ストレージ設定、SIEM、脅威の Intel API 設定の構成 (グローバルに適用)、詳細設定、自動ファイルアップロード、役割、デバイス グループ

    > [!NOTE]
    > この設定は、Microsoft Defender for Endpoint 管理者 (既定) の役割でのみ使用できます。

- **セキュリティ センターでセキュリティ設定** を管理する - アラート抑制設定の構成、オートメーション用のフォルダー除外の管理、オンボードデバイスとオフボード デバイスの管理、電子メール通知の管理、評価ラボの管理

- **ライブ応答機能**
    - **基本的な** コマンド:
        - ライブ応答セッションを開始する
        - リモート デバイスで読み取り専用のライブ応答コマンドを実行する (ファイルのコピーと実行を除く)
    - **高度な** コマンド:
        - ライブ応答を介してリモート デバイスからファイルをダウンロードする
        - ファイル ページから PE ファイルと PE 以外のファイルをダウンロードする
        - リモート デバイスにファイルをアップロードする
        - ファイル ライブラリからスクリプトを表示する
        - ファイル ライブラリからリモート デバイスでスクリプトを実行する

使用可能なコマンドの詳細については、「Live 応答を使用して [デバイスを調査する」を参照してください](live-response.md)。
  
## <a name="edit-roles"></a>ロールの編集

1. セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。

2. ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。

3. 編集する役割を選択します。

4. **[編集]** をクリックします。

5. 役割に割り当てられている詳細またはグループを変更します。 

6. [保存 **して閉じる] をクリックします**。

## <a name="delete-roles"></a>役割の削除

1. セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。

2. ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。

3. 削除する役割を選択します。

4. ドロップダウン ボタンをクリックし、[役割の削除] **を選択します**。

## <a name="related-topic"></a>関連トピック

- [ポータルにアクセスするためのユーザーの基本的なアクセス許可](basic-permissions.md)
- [デバイス グループの作成と管理](machine-groups.md)
