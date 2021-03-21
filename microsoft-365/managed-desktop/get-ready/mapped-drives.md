---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922910"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、マップされたドライブを準備する

多くのエンタープライズ環境では、マップされたドライブに関する従来の要件を満たして、ユーザーまたはチームがファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。 Microsoft では、Microsoft Managed Desktop でマップされたドライブを使用することをお勧めしません。 代わりに、次のようにファイル アクセス ソリューションを最新化することをお勧めします。
  
- 個々のユーザーが使用するマップされたドライブを OneDrive for Business に移行します。 
- チームが使用するマップされたドライブを移行して、ファイルを SharePoint Online に共有します。 
- オンプレミスのファイル共有を使用するアプリケーションを最新化または置き換え、その要件を削除します。
  
これらのサービスを最新化すると、Microsoft Managed Desktop で最高のユーザー エクスペリエンスを提供できます。 Microsoft FastTrack Services は、Microsoft Cloud Services を使用して環境を最新化する場合に役立ちます。 FastTrack サービスの対象かどうかを確認するには、「対象サービスとプラン」[](/fasttrack/m365-eligible-services-and-plans)を参照し、Microsoft マネージ デスクトップの準備のために直接お問い合わせください。 FastTrack OneDrive for Business または SharePoint Online 移行の背景については、「データ移行」 [を参照してください](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft Managed Desktop 上のマップされたドライブ
 
一部の使用例でマップされたドライブを削除または置き換えできない場合は、Microsoft Managed Desktop 管理ポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。
    
このような要求の場合は、サポート要求に次の詳細を入力する必要があります。 

- Microsoft Managed Desktop デバイスにマップする必要があるファイル共有場所へのすべての UNC パス 
- これらのファイル共有場所へのアクセスを必要とするユーザー グループ 
- 割り当てる必要がある特定のドライブ文字 (必要な場合)

次に例を示します。

| ドライブ文字 | UNC パス | ユーザー グループ |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持し、オンプレミスのファイル サービスにアクセス可能な状態を維持することは、完全にユーザーの責任です。 また、そのようなファイル共有の要件をできるだけ早く削除する必要があります。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop にマップされたドライブを展開するには
 
マップされたドライブを避けず、サービス要求を送信する前に要件を慎重に確認していることを確認してください。 次に、次の手順に従います。

1. [[Microsoft Endpoint Manager]](https://endpoint.microsoft.com/)に移動し、[トラブルシューティングとサポート] を選択し、[Microsoft 管理デスクトップ] セクションで [サービス要求] を探します。  
2. "マップされたドライブの展開" というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。  
3. Microsoft Managed Desktop IT Operations は、要求が完了したら、サポート要求の更新プログラムを使用して助言します。 最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。  
4. Microsoft Managed Desktop IT Operations によって展開された構成が期待通り動作するかどうかをテストして確認する必要があります。 テストが完了したら、同じサポート要求の詳細にある [ディスカッション] タブを使用して返信し、Microsoft Managed Desktop IT Operations に通知します。  
5. その後、Microsoft Managed Desktop IT Operations チームが構成を他の展開グループに展開します。