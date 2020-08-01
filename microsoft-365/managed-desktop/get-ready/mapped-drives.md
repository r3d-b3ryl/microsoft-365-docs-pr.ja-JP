---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: 確認のための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e6311c0ad11d68c870b0c8185974b8913735e2a2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530177"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、マップされたドライブを準備する

多くのエンタープライズ環境には、マップされたドライブに対する従来の要件があります。これにより、ユーザーまたはチームは、ファイルを共有および保存したり、オンプレミスのアプリケーションを使用したりできます。 Microsoft では、マップされたドライブを Microsoft マネージドデスクトップと共に使用することはお勧めしません。 代わりに、ファイルアクセスソリューションを次のように改革することをお勧めします。
  
- 個別のユーザーによって使用されるマップされたドライブを OneDrive for Business に移行します。 
- Teams で使用されるマップされたドライブを移行して、ファイルを SharePoint Online に共有します。 
- オンプレミスのファイル共有を使用するアプリケーションを近代化またはリプレースして、その要件を削除します。
  
モダン化これらのサービスを使用すると、Microsoft マネージドデスクトップでのエンドユーザーの操作を最高にすることができます。 Microsoft FastTrack サービスは、Microsoft クラウドサービスを使用してお客様の環境をモダン化するのに役立ちます。 必要な[サービスおよびプラン](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)で fasttrack サービスの対象となっているかどうかを確認してから、Microsoft マネージドデスクトップの準備のために直接連絡することができます。 FastTrack OneDrive for Business または SharePoint Online の移行の背景については、「[データ移行](https://docs.microsoft.com/fasttrack/o365-data-migration)」を参照してください。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップでのマップされたドライブ
 
一部のユースケースでマップされたドライブを削除または置換できない場合は、microsoft Managed Desktop 管理ポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。
    
このような要求では、サポート要求に次の詳細情報を提供する必要があります。 

- Microsoft マネージドデスクトップデバイスにマップする必要があるファイル共有場所へのすべての UNC パス 
- これらのファイル共有場所へのアクセスを必要とするユーザーグループ 
- 割り当てる必要がある特定のドライブ文字 (必要な場合)

例:

| ドライブ文字 | UNC パス | ユーザーグループ |
|--------------|----------|------------|
| エックス  | \\\ \ \ sharepoint/マーケティング | ContosoMarketing |

ユーザーやグループがファイル共有の場所にアクセスするための適切なアクセス許可を持っており、オンプレミスのファイルサービスにアクセスできることを確認するのは完全に責任があります。 また、このようなファイル共有の要件をできるだけ早く削除する必要があります。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップにマップされたドライブを展開するには
 
マップされたドライブを使用しないようにして、サービスリクエストを提出する前に要件を慎重に確認してください。 その後、次の手順を実行します。

1. [Microsoft マネージドデスクトップポータル](https://aka.ms/mmdportal)に移動します。  
2. 「Support **> support requests** 」セクションから「マップされたドライブの展開」というタイトルのサポート要求を送信し、必要なファイル共有の詳細をすべて提供します。  
3. Microsoft マネージドデスクトップ IT 操作は、要求が完了したときに、サポート要求の更新を使用してアドバイスします。 最初は、この構成はテスト展開グループのデバイスにのみ展開されます。  
4. Microsoft マネージドデスクトップの IT 運用によって展開された構成が期待どおりに動作するかどうかをテストし、確認する必要があります。 テストが完了したら、サポート要求の [ディスカッション] タブを使用して、Microsoft Managed Desktop IT Operations に通知します。  
5. Microsoft Managed Desktop IT 運用チームは、その構成を他の展開グループに展開します。 
