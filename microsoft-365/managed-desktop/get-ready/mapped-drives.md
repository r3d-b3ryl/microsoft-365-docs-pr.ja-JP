---
title: Microsoft マネージドデスクトップのマップされたドライブの準備
description: 確認のための重要な手順
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079273"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのマップされたドライブの準備

多くのエンタープライズ環境には、マップされたドライブに対する従来の要件があります。これにより、ユーザーまたはチームは、ファイルを共有および保存したり、オンプレミスのアプリケーションを使用したりできます。 Microsoft では、マップされたドライブを Microsoft マネージドデスクトップと共に使用することはお勧めしません。 代わりに、yor ファイルアクセスソリューションを次のように改革することをお勧めします。
  
- 個別のユーザーによって使用されるマップされたドライブを OneDrive for Business に移行します。 
- Teams で使用されるマップされたドライブを移行して、ファイルを SharePoint Online に共有します。 
- オンプレミスのファイル共有を使用するアプリケーションを近代化またはリプレースして、その要件を削除します。
  
モダン化これらのサービスを使用すると、Microsoft マネージドデスクトップでのエンドユーザーの操作を最高にすることができます。 Microsoft FastTrack サービスは、Microsoft クラウドサービスを使用してお客様の環境をモダン化するのに役立ちます。 必要な[サービスおよびプラン](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)で fasttrack サービスの対象となっているかどうかを確認してから、Microsoft マネージドデスクトップの準備のために直接連絡することができます。 FastTrack OneDrive for Business または SharePoint Online の移行の背景については、「[データ移行](https://docs.microsoft.com/fasttrack/o365-data-migration)」を参照してください。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップでのマップされたドライブ
 
一部のユースケースでマップされたドライブを削除または置換できない場合は、microsoft マネージドデスクトップポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。
    
このような要求では、サポート要求に次の詳細情報を提供する必要があります。 

- Microsoft マネージドデスクトップデバイスにマップする必要があるファイル共有場所へのすべての UNC パス 
- これらのファイル共有場所へのアクセスを必要とするユーザーグループ 
- 割り当てる必要がある特定のドライブ文字 (必要な場合)

次に例を示します。

| ドライブ文字 | UNC パス | ユーザーグループ |
|--------------|----------|------------|
| エックス  | \\\ \ \ sharepoint/マーケティング | ContosoMarketing |

ユーザーやグループがファイル共有の場所にアクセスするための適切なアクセス許可を持っており、オンプレミスのファイルサービスにアクセスできることを確認するのは完全に責任があります。 また、このようなファイル共有の要件をできるだけ早く削除する必要があります。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップにマップされたドライブを展開するには
 
マップされたドライブを使用しないようにして、サービスリクエストを提出する前に要件を慎重に確認してください。 その後、次の手順を実行します。

1. [Microsoft マネージドデスクトップポータル](https://aka.ms/mmdportal)に移動します。  
2. 「 **Support _GT_ support requests** 」セクションに「マップされたドライブの展開」というタイトルのサポート要求を送信し、必要なファイル共有の詳細をすべて提供します。  
3. Microsoft マネージドデスクトップ操作では、要求が完了したときに、サポート要求の更新を使用してアドバイスします。 最初は、この構成はテスト展開グループのデバイスにのみ展開されます。  
4. Microsoft Managed Desktop Operations team が展開した構成が期待どおりに動作するかどうかをテストし、確認する必要があります。 テストが完了したら、サポート要求を使用して Microsoft マネージドデスクトップの操作を更新します。  
5. Microsoft Managed Desktop Operations team は、その構成を他の展開グループに展開します。 