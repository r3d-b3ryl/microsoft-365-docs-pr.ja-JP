---
title: メールによる共同作業
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- MOW150
- OWE150
- OWP150
- SPO160
- BSA160
- SPB160
ms.assetid: eb3e840f-ed60-4461-81f5-12381c132b89
description: さまざまな種類のグループと、Microsoft 365のさまざまなコラボレーション機能でグループを使用する方法について説明します。
ms.openlocfilehash: dd320b51d538a3dff7ed539d11139d398980ca2e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164982"
---
# <a name="email-collaboration"></a>メールによる共同作業

Microsoft 365は、Outlook、配布リスト (配布グループとも呼ばれます)、共有メールボックス、パブリック フォルダー内のグループを通じてコラボレーションを促進します。 各オプションの目的、操作性、機能セットは、それぞれ異なります。 どのように利用するのかは、ユーザーのニーズや組織が提供するツールによります。
  
## <a name="summary-of-collaboration-options"></a>共同作業オプションの概要
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、使用可能なさまざまなコラボレーション オプションについて説明します。
  


|**共同作業ツール**|**説明**|
|:-----|:-----|
|Outlookのグループ  <br/> |Microsoft 365内のすべてのアプリケーションで動作する共有ワークスペース。 共有受信ボックス、予定表、ファイルを保存するための OneDrive for Business サイトなどが含まれます。 ユーザーは、メールや予定表から直接Outlookグループを作成、検索、参加できます。 Exchange OnlineまたはMicrosoft 365 サブスクリプションを持つ新規および既存のユーザーは、Outlookでグループを使用できます。  <br/> |
|共有メールボックス  <br/> |特定のユーザーがメール メッセージの閲覧と送信や共通の予定表の共有に使うメールボックスです。共有メールボックスは、顧客が問い合わせに利用する代表メール アドレス (info@contoso.com や sales@contoso.com など) にも使うことができます。代理人として送信するアクセス権が共有メールボックスに対して有効に設定されている場合、共有メールボックスから送信されるメールには、代表のアドレス (sales@contoso.com など) が使用されます。  <br/> |
|配布リスト (配布グループとも呼ばれる)  <br/> |メール メッセージを複数のユーザーに同時に配布するのに使用します。配布グループは、メール対応の配布グループとしても知られています。配布グループには、動的配布グループと呼ばれるグループもあります。これは、メール対応の Active Directory グループ オブジェクトで、大規模で進化する受信者グループにメールを送信するのに使用されます。正確な受信者は、特定ロケールのすべてのメンバーやすべての正社員など、指定したフィルターと条件によって決定されます。<br/><br/> OutlookのMicrosoft 365 グループは、配布グループよりもコラボレーションのためのより強力なソリューションを提供します。 詳細については、「[配布リストをOutlook内のグループにアップグレードする理由」と「配布リストをMicrosoft 365 グループ](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)[に移行する理由」を参照](../manage/upgrade-distribution-lists.md)してください。  <br/> |
|パブリック フォルダー  <br/> |共有アクセス用に設計されたパブリック フォルダーは、組織内の他のユーザーと情報を収集、整理、共有するための簡単で効果的な方法を提供します。 パブリック フォルダーでは、コンテンツが細分化された階層構造で編成され、Outlook のフォルダー ビューに常に表示されるので、簡単に参照できます。 パブリック フォルダーは、メールに対応でき、配布グループのメンバーとして追加できます。 配布グループに送信されたメールは、アーカイブや後で参照できるように、自動的にパブリック フォルダーに追加されます。 パブリック フォルダーは、SharePoint Online サブスクリプションを所有していない場合に、ドキュメントを簡単に共有する方法として利用することもできます。  <br/> |
   
## <a name="which-collaboration-tool-to-use"></a>用途から見た共同作業ツールの比較
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、さまざまな種類のグループを一目で確認し、それらをさまざまなコラボレーション機能で使用するタイミングと方法について説明します。
  

||**Outlookのグループ**|**配布リスト**|**共有メールボックス**|**パブリック フォルダー**|
|:-----|:-----|:-----|:-----|:-----|
|**ユーザーのタイプ** <br/> |既に使用しているサービスと統合されているグループ メッセージ、ファイル、予定表のコラボレーション ワークスペースを必要とするユーザー (Outlook Web App、OneDrive for Business)  <br/> |共通の関心または特徴を持つ受信者のグループに電子メールを送信する必要があるユーザー。  <br/> |共有メールボックスは、組織内の複数のユーザーがメールボックスを監視し、クエリに応答する責任を共有できるため、顧客の電子メールの質問を処理する優れた方法です。 顧客からの質問の回答が迅速になり、関連するメールはすべて 1 つのメールボックスに格納されます。  <br/><br/> 仮想 ID (support@contoso.com など) の代表として作業をする代表者。代表者は、共有メールボックス ID を使ってメールに返信できます。  <br/> |パブリック フォルダーのアクセスと検索に必要なアクセス権を持つ組織内のすべてのユーザー。パブリック フォルダーは、メールのアーカイブやドキュメントの共有に適しています。  <br/> |
|**理想的なグループ サイズ** <br/> |ANY  <br/> |LARGE  <br/> |小さな  <br/> |大規模な  <br/> |
|**Access** <br/> |Exchange Onlineとユーザー  <br/> |配布グループでは、メンバーを手動で追加する必要があります。動的配布グループでは、メンバーはフィルター条件に基づいて追加されます。  <br/> |ユーザーには、フル アクセス権や代理人として送信するアクセス権を割り当てることができます。フル アクセス権が割り当てられたユーザーは、共有メールボックスにアクセスするために、共有メールボックスを Outlook プロファイルに追加する必要があります。  <br/> |組織内のすべてのユーザーがアクセスできます  <br/> |
|**共有予定表** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |はい  <br/> |
|**メールはユーザーの個人用受信トレイに配信されるか?** <br/> |いいえ、ユーザーがグループにサブスクライブすると、すべてのグループ メッセージがユーザーの受信トレイに配信されます。  <br/> |はい、メールは配布グループのすべてのメンバーの受信トレイに配信されます。  <br/> |いいえ、メールは共有メールボックスの受信トレイに配信されます。  <br/> |いいえ、メールはパブリック フォルダーに配信されます。  <br/> |
|**サポート対象のクライアント アプリケーション** <br/> | Outlook 2016  <br/>  Outlook 2013 (サブスクライブ後に転送)  <br/>  Outlook Web App  <br/>  Outlook 2010 (サブスクライブ後に転送)  <br/>  Outlook 2007 (サブスクライブ後に転送)  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> |

  
## <a name="related-articles"></a>関連記事

[配布グループの管理](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
    
[サイト メールボックスの代わりにMicrosoft 365 グループを使用する](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)
    
[Microsoft 365で共有メールボックスを作成する](create-a-shared-mailbox.md)
    
[Microsoft 365とExchange Onlineのパブリック フォルダー](/exchange/collaboration-exo/public-folders/public-folders)
