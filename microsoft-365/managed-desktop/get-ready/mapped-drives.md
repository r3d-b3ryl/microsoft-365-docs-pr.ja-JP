---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認する重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841066"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、マップされたドライブを準備する

多くのエンタープライズ環境には、マップされたドライブに関するレガシ要件があります。この要件により、ユーザーやチームはファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。 Microsoft では、Microsoft マネージド デスクトップでマップされたドライブを使用することを推奨しません。 代わりに、ファイル アクセス ソリューションを次のようにモダン化することをお勧めします。
  
- 個々のユーザーが使用するマップされたドライブを OneDrive for Business に移行します。 
- チームがファイルを共有するために使用するマップされたドライブを SharePoint Online に移行します。 
- オンプレミスのファイル共有を使用するアプリケーションをモダン化または置換して、その要件を削除します。
  
これらのサービスをモダン化すると、Microsoft マネージド デスクトップで最適なユーザー エクスペリエンスを提供できます。 Microsoft FastTrack サービスは、Microsoft クラウド サービスを使用して環境をモダン化する場合に役立ちます。 対象となるサービスとプランで FastTrack サービスの対象かどうかを確認[](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)し、Microsoft マネージド デスクトップの準備のために直接お問い合わせください。 FastTrack OneDrive for Business または SharePoint Online 移行の背景情報については、「データ移行」 [を参照してください](https://docs.microsoft.com/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ上のマップされたドライブ
 
一部の使用例で、マップされたドライブを削除または置換できない場合は、Microsoft マネージド デスクトップ管理ポータルでサポート要求を送信して、Microsoft マネージド デスクトップ ユーザーに展開する必要があります。
    
このような要求の場合は、サポート要求に次の詳細を入力する必要があります。 

- Microsoft マネージド デスクトップ デバイスにマップする必要があるファイル共有の場所へのすべての UNC パス 
- これらのファイル共有の場所へのアクセスが必要なユーザー グループ 
- 割り当てる必要がある特定のドライブ文字 (必要な場合)

例:

| ドライブ文字 | UNC パス | ユーザー グループ |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持し、オンプレミスのファイル サービスにアクセス可能なままにすることは、完全にユーザーの責任です。 また、このようなファイル共有の要件はできるだけ早く削除する必要があります。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップにマップされたドライブを展開するには
 
マップされたドライブを回避できないことを確認し、サービス要求を送信する前に要件を慎重に確認してください。 次の手順に従います。

1. Microsoft [Endpoint Manager に移動](https://endpoint.microsoft.com/) し、[トラブルシューティング + サポート] を選択し、[Microsoft マネージド デスクトップ] セクションで [サービス要求] を探します。  
2. 「マップされたドライブの展開」というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。  
3. Microsoft マネージド デスクトップ IT 運用は、要求が完了したら、サポート要求の更新を使用してアドバイスします。 最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。  
4. Microsoft マネージド デスクトップ IT 操作によって展開された構成が期待通り動作するかどうかをテストして確認する必要があります。 テストが完了したら、同じサポート要求の詳細にある [ディスカッション] タブを使用して返信し、Microsoft マネージド デスクトップ IT 操作に通知します。  
5. その後、Microsoft マネージド デスクトップ IT 運用チームは、構成を他の展開グループに展開します。 
