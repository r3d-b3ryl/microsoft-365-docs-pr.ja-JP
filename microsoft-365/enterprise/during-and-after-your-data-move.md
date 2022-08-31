---
title: データの移行中および移行後
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/02/2022
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
ms.localizationpriority: medium
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: データの移動は、Microsoft がテナントのサービスと関連データを新しいデータセンター geo に移動するときに発生するバックエンド操作です。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c8b22665fec704ae9cb74bb2fe218e0b2e4a00f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478599"
---
# <a name="during-and-after-your-data-move"></a>データの移行中および移行後

データの移動はバックエンド操作であり、エンド ユーザーへの影響は最小限です。 Microsoft が各サービスとお客様のテナントの関連データを新しいデータセンター geo に移動する際には、何も行う必要はありません。 データの転送および検証は事前にバックグラウンドで行われ、ユーザーへの影響は最小限に抑えられます。
  
> [!NOTE]
> 移動はサービスごとに、異なる時間に行われます。結果として、サービスごとに異なる時間に、説明されているような機能制限がかかります。
  
Exchange Online、SharePoint Online、Teams チャット サービスの各移動が完了したら、Microsoft 365 メッセージ センターで確認してください。 次の表に示すように、登録期間の終わりから最大 24 か月後に、保存時のコア 顧客データが新しいデータセンター geo に移行されるまでに最大で 24 か月かかる場合があります。

| サインアップ国をお持ちのお客様 | 完了したすべての移動 |
|:-----|:-----|
|オーストラリア、ニュージーランド、フィジー  <br/> |2022 年 7 月 1 日  <br/> |
|日本  <br/> |2022 年 7 月 1 日  <br/> |
|インド  <br/> |2022 年 7 月 1 日  <br/> |
|カナダ  <br/> |2022 年 7 月 1 日  <br/> |
|韓国  <br/> |2022 年 7 月 1 日  <br/> |
|英国  <br/> |2022 年 7 月 1 日  <br/> |
|フランス  <br/> |2022 年 7 月 1 日  <br/> |
|アラブ首長国連邦  <br/> |2022 年 7 月 1 日  <br/> |
|南アフリカ  <br/> |2022 年 7 月 1 日  <br/> |
|スイス、リヒテンシュタイン  <br/> |2022 年 7 月 1 日  <br/> |
|ノルウェー  <br/> |2022 年 11 月 1 日  <br/> |
|ドイツ  <br/> |2023 年 5 月 1 日  <br/> |
|ブラジル  <br/> |2023 年 6 月 1 日  <br/> |
|スウェーデン  <br/> |2024 年 6 月 1 日  <br/> |
|カタール  <br/> |2025 年 3 月 1 日  <br/> |

## <a name="exchange-online"></a>Exchange Online

各ユーザーをシングル テナントの新しいデータセンター geo に移動するのに時間がかかるため、移動中は一部のユーザーが古いデータセンター geo のまま、他のユーザーは新しいデータセンター geo という状態になります。 つまり、複数のメールボックスへのアクセスを伴う一部の機能は、移動プロセスの期間中は完全に機能しない可能性があります。これは数週間続く可能性があります。 該当する機能については、この後のセクションで取り上げます。
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Outlook Web Access で "共有フォルダー" を開く

一部のユーザーは、Outlook Web Access で "共有フォルダー" 機能を使用して、別のメールボックスから共有メール フォルダー (ユーザーが読み取りまたは書き込みアクセス許可を持つフォルダー) を開きます。次の表に、メールボックスの移動中に、共有フォルダーへのアクセス権がどのように動作するかを取り上げます。共有メールボックスへのフル アクセス許可があるユーザーは、移動中に Outlook Web Access を使用してメールボックスを開くことができます。
  
| 構成 | 説明 |
|:-----|:-----|
|別のメールボックスへのメールボックス フォルダー アクセス許可があるユーザー  <br/> |制限される可能性があります。  <br/> テナントの移動中にユーザー A とメールボックス B が同じ geo になく、ユーザー A が持っているアクセス許可がメールボックス B の特定のフォルダーに対してのみの場合、ユーザー A は Outlook Web Access でメールボックス B のフォルダーを開くことができません。  <br/> 共有フォルダーを追加するには、左側のナビゲーション ウィンドウでユーザー名を右クリックし、 **[共有フォルダーの追加]** を選択します。  <br/> |
|別のメールボックスへのメールボックス フル アクセス許可があるユーザー  <br/> |完全にサポートされます。  <br/> ユーザー A にメールボックス B への "フル アクセス" アクセス許可がある場合、ユーザー A は Outlook Web Access の左側のナビゲーション パネルで共有フォルダーをクリックして、メールボックス B を示すウィンドウを開くことができます。 ユーザーは、移動中に Outlook Web Access を使用して共有メールボックスを開くことができます。悪影響はありません。 制限は、メールボックス内のフォルダー レベルの共有だけに適用されます。           |
  
## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online を移行すると、以下のサービスのデータも移行されます。
  
- OneDrive for Business

- Microsoft 365 ビデオ サービス

- ブラウザー版 Office

- Microsoft 365 Apps for enterprise

- Visio Pro for Microsoft 365

SharePoint Online データの移動が完了すると、次のような効果が表示される場合があります。
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Video Services

- ビデオのデータの移動は、SharePoint Online にある残りのコンテンツの移動より時間がかかります。

- SharePoint Online のコンテンツを移行すると、ビデオが再生できない時間が生じます。

- 以前のデータセンターからコード変換されたコピーを削除し、新しいデータセンターでコードを再変換しています。

### <a name="search"></a>検索

SharePoint Online データを移行する過程で、検索インデックスと検索設定を新しい場所に移行します。 SharePoint Onlineデータの移行が **完了** するまで、ユーザーは引き続き元の場所でインデックスを利用できます。 SharePoint Online データの移行が完了すると、新しい場所で、検索機能によってコンテンツのクロールが自動的に再開されます。 これより以降、ユーザーは移行したインデックスを利用できます。 移行後に生じたコンテンツの変更は、クロールで反映されるまで移行したインデックスに組み込まれません。 ほとんどのお客様は、SharePoint Online データの移動が完了した直後は結果が少ないことに気付いていませんが、最初の 24 ~ 48 時間で鮮度が低下する可能性があります。
  
次の検索機能が影響を受けます。
  
- 検索結果と検索 Web パーツ:移行後に生じた変更は、クロールで反映されるまで結果に含まれません。 

- Delve:移行後に生じた変更は、クロールで反映されるまで Delve に含まれません。

- サイトの人気と検索に関するレポート: 新しい場所での Excel レポートのカウントには、移行した数、および SharePoint Online データの移行完了後に実行された利用状況レポートの数のみが含まれます。中間の期間の数はすべて失われ、回復することはできません。この期間は、通常、2、3 日です。顧客によっては情報が失われている期間が増減することもあります。

- ビデオ ポータル:ビデオ ポータルの表示回数と統計情報は Excel レポートの統計情報に基づいているため、ビデオ ポータルの表示回数と統計情報は、Excel レポートと同じ期間失われます。

- 電子情報開示:移行中に変更されたアイテムは、クロールで変更が反映されるまでは表示されません。

- データ損失防止 (DLP):クロールで変更が反映されるまで、変更されたアイテムに対してポリシーは適用されません。

移行の一環として、既定のリージョンが変更され、すべての新しいコンテンツが新しい既定のリージョンに保存されます。 既存のコンテンツは、管理センターの SharePoint Online データの場所に最初に変更された後、最大 90 日間、影響を受けず、バックグラウンドで移動します。

## <a name="microsoft-teams"></a>Microsoft Teams

### <a name="files-tab"></a>[ファイル] タブ

移行が完了すると、[ファイル] タブで、ユーザーが最初に使用を試みたときに完全に読み込まれるまでさらに時間がかかる場合があります (最大 7 秒)。 

### <a name="read-only-period"></a>読み取り専用期間

Teams チャット サービスは、各スレッドを個別に移動します。  スレッドは移動中に読み取り専用状態でロックされ、スレッドごとに数秒続きます。  スレッドは移行中も引き続きアクセスできます。

## <a name="skype-for-business"></a>Skype for Business

Skype for Business移動は使用できなくなりました。  [Skype for Business Online は](/lifecycle/announcements/skype-for-business-online-retirement) 2021 年 7 月 31 日に廃止されます。 この日以降は、サービスにアクセスできなくなります。
  
## <a name="related-topics"></a>関連項目

[データ移行を申請する方法](request-your-data-move.md)

[データ移行についての一般的な FAQ](data-move-faq.md)
  
[Microsoft Dynamics CRM Online の新しいデータ センター geo](/power-platform/admin/new-datacenter-regions)
  
[Azure のリージョン](https://azure.microsoft.com/regions/)
