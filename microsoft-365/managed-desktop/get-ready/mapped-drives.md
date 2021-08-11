---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: マップされたドライブ上のデータにユーザーがアクセスできる重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d272c08287dd6198d4c33b4d1df3ff8662eda12781d676b75c93189d08409de7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819093"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、マップされたドライブを準備する

多くのエンタープライズ環境では、マップされたドライブに関する従来の要件を満たして、ユーザーまたはチームがファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。 Microsoft では、マップされたドライブを使用してデバイスを使用Microsoft マネージド デスクトップ。 代わりに、次のようにファイル アクセス ソリューションを最新化することをお勧めします。
  
- 個々のユーザーが使用するマップされたドライブを、OneDrive for Business。 
- チームがファイルを共有するために使用するマップされたドライブをオンラインにSharePointします。 
- オンプレミスのファイル共有を使用するアプリケーションを最新化または置き換え、その要件を削除します。
  
これらのサービスを最新化すると、ユーザー エクスペリエンスが最適Microsoft マネージド デスクトップ。 Microsoft FastTrack Services は、Microsoft Cloud Services を使用して環境を最新化する場合に役立ちます。 FastTrack サービスの対象かどうかは、「対象サービスとプラン」で[](/fasttrack/m365-eligible-services-and-plans)確認し、直接連絡してサービスの準備Microsoft マネージド デスクトップ。 FastTrack OneDrive for BusinessまたはオンラインSharePointの背景については、「データ移行」[を参照してください](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>マップされたドライブMicrosoft マネージド デスクトップ
 
一部の使用例でマップされたドライブを削除または置き換えできない場合は、Microsoft マネージド デスクトップ 管理ポータルでサポート要求を送信して、Microsoft マネージド デスクトップ ユーザーに展開する必要があります。
    
このような要求の場合は、サポート要求に次の詳細を入力する必要があります。 

- デバイスにマップする必要があるファイル共有の場所へのすべての UNC パスMicrosoft マネージド デスクトップします。 
- これらのファイル共有場所へのアクセスを必要とするユーザー グループ 
- 割り当てる必要がある特定のドライブ文字 (必要な場合)

次に例を示します。

| ドライブ文字 | UNC パス | ユーザー グループ |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持し、オンプレミスのファイル サービスにアクセス可能な状態を維持することは、完全にユーザーの責任です。 また、そのようなファイル共有の要件をできるだけ早く削除する必要があります。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>マップされたドライブをネットワークに展開するにはMicrosoft マネージド デスクトップ
 
マップされたドライブを避けず、サービス要求を送信する前に要件を慎重に確認していることを確認してください。 次に、次の手順に従います。

1. [サービス] [Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/)に移動し、[トラブルシューティングとサポート] を選択し、[サービス要求] セクションの [サービス要求] をMicrosoft マネージド デスクトップします。  
2. "マップされたドライブの展開" というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。  
3. Microsoft マネージド デスクトップIT 運用は、要求が完了したら、サポート 要求の更新プログラムを使用して助言します。 最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。  
4. IT 運用が期待した通り機能するために、Microsoft マネージド デスクトップ構成をテストして確認する必要があります。 テストが完了したら、同じサポート要求の詳細にある [ディスカッション] タブをMicrosoft マネージド デスクトップして、IT 運用に通知します。  
5. Microsoft マネージド デスクトップその後、IT 運用チームは構成を他の展開グループに展開します。 

## <a name="steps-to-get-ready"></a>準備の手順

1. 詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)
2. [準備状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [マップされたドライブをMicrosoft マネージド デスクトップ](mapped-drives.md)する (この記事)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
