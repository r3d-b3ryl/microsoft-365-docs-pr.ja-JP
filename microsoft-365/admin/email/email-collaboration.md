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
description: さまざまな種類のグループについて、およびグループのさまざまなコラボレーション機能でグループを使用する方法についてMicrosoft 365。
ms.openlocfilehash: dd320b51d538a3dff7ed539d11139d398980ca2e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164982"
---
# <a name="email-collaboration"></a>メールによる共同作業

Microsoft 365グループ、配布Outlook (配布グループとも呼ばれる)、共有メールボックス、およびパブリック フォルダーでのグループによるコラボレーションを推奨します。 各オプションの目的、操作性、機能セットは、それぞれ異なります。 どのように利用するのかは、ユーザーのニーズや組織が提供するツールによります。
  
## <a name="summary-of-collaboration-options"></a>共同作業オプションの概要
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、使用可能なさまざまなコラボレーション オプションについて説明します。
  


|**共同作業ツール**|**説明**|
|:-----|:-----|
|グループのOutlook  <br/> |すべてのアプリケーションで動作する共有ワークスペースは、Microsoft 365。 共有受信ボックス、予定表、ファイルを保存するための OneDrive for Business サイトなどが含まれます。 ユーザーは、メールまたは予定表から、Outlookグループを作成、検索、参加できます。 新しいユーザーと既存のユーザーは、Exchange OnlineサブスクリプションMicrosoft 365グループを使用Outlook。  <br/> |
|共有メールボックス  <br/> |特定のユーザーがメール メッセージの閲覧と送信や共通の予定表の共有に使うメールボックスです。共有メールボックスは、顧客が問い合わせに利用する代表メール アドレス (info@contoso.com や sales@contoso.com など) にも使うことができます。代理人として送信するアクセス権が共有メールボックスに対して有効に設定されている場合、共有メールボックスから送信されるメールには、代表のアドレス (sales@contoso.com など) が使用されます。  <br/> |
|配布リスト (配布グループとも呼ばれる)  <br/> |メール メッセージを複数のユーザーに同時に配布するのに使用します。配布グループは、メール対応の配布グループとしても知られています。配布グループには、動的配布グループと呼ばれるグループもあります。これは、メール対応の Active Directory グループ オブジェクトで、大規模で進化する受信者グループにメールを送信するのに使用されます。正確な受信者は、特定ロケールのすべてのメンバーやすべての正社員など、指定したフィルターと条件によって決定されます。<br/><br/> Microsoft 365グループは、Outlookグループよりも強力なコラボレーションソリューションを提供します。 詳細については、「配布リストを[グループ](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)にアップグレードする理由」および「Outlookグループに配布リストを移行する」[をMicrosoft 365してください](../manage/upgrade-distribution-lists.md)。  <br/> |
|パブリック フォルダー  <br/> |共有アクセス用に設計されたパブリック フォルダーは、組織内の他のユーザーと情報を収集、整理、および共有するための簡単かつ効果的な方法を提供します。 パブリック フォルダーでは、コンテンツが細分化された階層構造で編成され、Outlook のフォルダー ビューに常に表示されるので、簡単に参照できます。 パブリック フォルダーは、メールに対応でき、配布グループのメンバーとして追加できます。 配布グループに送信されたメールは、アーカイブや後で参照できるように、自動的にパブリック フォルダーに追加されます。 パブリック フォルダーは、SharePoint Online サブスクリプションを所有していない場合に、ドキュメントを簡単に共有する方法として利用することもできます。  <br/> |
   
## <a name="which-collaboration-tool-to-use"></a>用途から見た共同作業ツールの比較
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、さまざまな種類のグループを一目で確認し、それらをさまざまなコラボレーション機能で使用する場合と方法について説明します。
  

||**グループのOutlook**|**配布リスト**|**共有メールボックス**|**パブリック フォルダー**|
|:-----|:-----|:-----|:-----|:-----|
|**ユーザーのタイプ** <br/> |既に使用しているサービスと統合されたグループ メッセージ、ファイル、および予定表のコラボレーション ワークスペースを必要とするユーザー (Outlook Web App、OneDrive for Business)  <br/> |共通の関心または特徴を持つ受信者のグループに電子メールを送信する必要があるユーザー。  <br/> |共有メールボックスは、組織内のいくつかのユーザーがメールボックスを監視し、クエリに応答する責任を共有できるので、顧客の電子メールの質問を処理するための最適な方法です。 顧客の質問は、より迅速な回答を得て、関連する電子メールはすべて 1 つのメールボックスに格納されます。  <br/><br/> 仮想 ID (support@contoso.com など) の代表として作業をする代表者。代表者は、共有メールボックス ID を使ってメールに返信できます。  <br/> |パブリック フォルダーのアクセスと検索に必要なアクセス権を持つ組織内のすべてのユーザー。パブリック フォルダーは、メールのアーカイブやドキュメントの共有に適しています。  <br/> |
|**理想的なグループ サイズ** <br/> |ANY  <br/> |LARGE  <br/> |小さな  <br/> |大規模な  <br/> |
|**Access** <br/> |Exchange Onlineユーザー  <br/> |配布グループでは、メンバーを手動で追加する必要があります。動的配布グループでは、メンバーはフィルター条件に基づいて追加されます。  <br/> |ユーザーには、フル アクセス権や代理人として送信するアクセス権を割り当てることができます。フル アクセス権が割り当てられたユーザーは、共有メールボックスにアクセスするために、共有メールボックスを Outlook プロファイルに追加する必要があります。  <br/> |組織内のすべてのユーザーがアクセスできます  <br/> |
|**共有予定表** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |はい  <br/> |
|**メールはユーザーの個人用受信トレイに配信されるか?** <br/> |いいえ、ユーザーがグループにサブスクライブすると、すべてのグループ メッセージがユーザーの受信トレイに配信されます。  <br/> |はい、メールは配布グループのすべてのメンバーの受信トレイに配信されます。  <br/> |いいえ、メールは共有メールボックスの受信トレイに配信されます。  <br/> |いいえ、メールはパブリック フォルダーに配信されます。  <br/> |
|**サポート対象のクライアント アプリケーション** <br/> | Outlook 2016  <br/>  Outlook 2013 (サブスクライブ後に転送)  <br/>  Outlook Web App  <br/>  Outlook 2010 (サブスクライブ後に転送)  <br/>  Outlook 2007 (サブスクライブ後に転送)  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> |

  
## <a name="related-articles"></a>関連記事

[配布グループの管理](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
    
[サイト Microsoft 365代わりにグループを使用する](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)
    
[共有メールボックスを作成Microsoft 365](create-a-shared-mailbox.md)
    
[パブリック フォルダー (Microsoft 365 および Exchange Online](/exchange/collaboration-exo/public-folders/public-folders)
