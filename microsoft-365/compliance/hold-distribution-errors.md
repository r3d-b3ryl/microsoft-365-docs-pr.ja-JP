---
title: 電子情報開示の保持エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: コア電子情報開示の保管担当者および非保管データ ソースに適用される法的ホールドに関連するエラーのトラブルシューティングを行います。
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860388"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>電子情報開示の保持エラーのトラブルシューティング

この記事では、電子情報開示ホールドで発生する可能性のある一般的な問題と、それらを解決する方法について説明します。 この記事には、これらの問題を軽減または回避するための推奨プラクティスも含まれています。

## <a name="recommended-practices"></a>推奨プラクティス

電子情報開示ホールドに関連するエラーの数を減らすには、次の方法をお勧めします。

- 保留配布がまだ保留中の場合は、保留配布が完了するまで待機してから、それ以上の更新 `On (Pending)` `Off (Pending)` を行います。

- トランザクションごとに保持ポリシーを繰り返し更新するのではなく、1 つの一括要求で更新プログラムを電子情報開示保留にマージします。 [たとえば、Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy)コマンドレットを使用して既存の保持ポリシーに複数のユーザー メールボックスを追加するには、コマンドを実行 (またはスクリプトにコード ブロックとして追加) して、複数のユーザーを追加するために 1 回だけ実行します。

  **正しい例**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **正しくない例**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   前の不適切な例では、コマンドレットを 5 回実行してタスクを完了します。 ユーザーを保留ポリシーに追加するための推奨プラクティスの詳細については、「詳細」 [セクションを参照](#more-information) してください。

- 電子情報開示ホールドの問題について Microsoft サポートに問い合わせする前に、「エラー [/問題:](#errorissue-holds-dont-sync) 保留リストは同期しない」セクションの手順に従って、保留配布を再試行してください。 このプロセスでは、多くの場合、内部サーバー エラーなどの一時的な問題が解決されます。

## <a name="errorissue-holds-dont-sync"></a>エラー/問題: 保留は同期されません

保管担当者とデータ ソースを保留にするときに次のエラー メッセージが表示される場合は、解決手順を使用して問題のトラブルシューティングを行います。

> リソース: ポリシーの展開に予想以上に時間がかかります。 最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。

> データセンターの一時的な問題により、ポリシーをコンテンツ ソースOffice 365できません。 現在のポリシーはソース内のコンテンツには適用されないので、ブロックされた展開による影響はありません。 この問題を解決するには、ポリシーを再展開してみてください。

> 申し訳ございませんが、一時的な内部サーバー エラーのため、ポリシーに対して要求された変更を実行できません。 30 分後にもう一度お試しください。

### <a name="resolution"></a>解決方法

1. Connectコンプライアンス センター [powerShell &に移動](/powershell/exchange/connect-to-scc-powershell)し、電子情報開示ホールドに対して次のコマンドを実行します。

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. *DistributionDetail パラメーターの値を調* べてください。 次のようなエラーを探します。

   > エラー: リソース: ポリシーの展開に予想以上に時間がかかります。 最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。

3. 問題の **保留ポリシーで Set-CaseHoldPolicy -RetryDistribution** コマンドを実行してみてください。例えば：

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>詳細情報

- 「推奨されるプラクティス」セクションの複数のユーザーの保留ポリシーの更新に関するガイダンスは、システムが保留ポリシーへの同時更新をブロックしているという事実から生じます。 つまり、更新された保留ポリシーが新しいコンテンツの場所に適用され、保留ポリシーが保留中の状態である場合、追加のコンテンツの場所を保留ポリシーに追加できない。 この問題の軽減に役立ついくつかの注意が必要な情報を次に示します。
  
  - 更新された保留が更新されるたび、保留状態に直ちに入ります。 保留中の状態は、保留がコンテンツの場所に適用されている状態を意味します。
  
  - ループを実行し、ポリシーに場所を 1 つ 1 つ追加するスクリプトがある場合 (「推奨されるプラクティス」セクションに示されている不適切な例と同様)、最初のコンテンツの場所 (ユーザー メールボックスなど) が、保留中の状態をトリガーする同期プロセスを開始します。 つまり、後続のループでポリシーに追加された他のユーザーはエラーになります。
  
  - 組織がループを実行して保留ポリシーのコンテンツの場所を更新するスクリプトを使用している場合は、スクリプトを更新して、単一の一括操作で場所を更新する必要があります (「推奨されるプラクティス」セクションの正しい例に示すように)。
