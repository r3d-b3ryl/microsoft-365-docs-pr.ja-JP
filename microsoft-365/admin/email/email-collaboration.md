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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
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
description: さまざまな種類のグループについて、およびそれらを Microsoft 365 のさまざまなコラボレーション機能と組み合わせて使用する方法について説明します。
ms.openlocfilehash: d48f92380715153a28553f959f402faa7ae77f4c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780231"
---
# <a name="email-collaboration"></a>メールによる共同作業

Microsoft 365 は、Outlook のグループ、配布リスト (配布グループとも呼ばれます)、共有メールボックス、およびパブリックフォルダーを使用してコラボレーションを促進します。 各オプションの目的、操作性、機能セットは、それぞれ異なります。 どのように利用するのかは、ユーザーのニーズや組織が提供するツールによります。
  
## <a name="summary-of-collaboration-options"></a>共同作業オプションの概要
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、さまざまなコラボレーションオプションについて説明します。
  


|**共同作業ツール**|**説明**|
|:-----|:-----|
|Outlook のグループ  <br/> |Microsoft 365 のすべてのアプリケーションで動作する共有ワークスペース。 共有受信ボックス、予定表、ファイルを保存するための OneDrive for Business サイトなどが含まれます。 ユーザーは、電子メールまたは予定表から Outlook の直接グループを作成、検索、および参加することができます。 Exchange Online または Microsoft 365 サブスクリプションを使用する新規および既存のユーザーは、Outlook でグループを使用できます。  <br/> |
|共有メールボックス  <br/> |A mailbox for select users to read and send email messages and share a common calendar. Shared mailboxes also can serve as a generic email address (such as info@contoso.com or sales@contoso.com) that customers can use to inquire about your company. When the Send As permission is enabled on the shared mailbox, email sent from the mailbox will use the generic address (e.g., sales@contoso.com).  <br/> |
|配布リスト (配布グループとも呼ばれる)  <br/> |Used to distribute email messages to two or more people at the same time. Distribution groups are also known as mail-enabled distribution groups. A variant of the distribution group, called the dynamic distribution group, is a mail-enabled Active Directory group object used to send email to a large and evolving group of recipients. The exact recipients are determined by filters and conditions that you specify, such as all members of a particular locale or all full-time employees.   <br/><br/> Outlook の Microsoft 365 グループは、配布グループと比較して、より強力なコラボレーションソリューションを提供しています。 詳細については、「[配布リストを Outlook のグループにアップグレード](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)して、[配布リストを Microsoft 365 グループに移行](../manage/upgrade-distribution-lists.md)する理由」を参照してください。  <br/> |
|パブリック フォルダー  <br/> |共有アクセスのために設計されたパブリックフォルダーは、組織内の他のユーザーと情報を収集、整理、共有するための簡単で効果的な方法を提供します。 パブリック フォルダーでは、コンテンツが細分化された階層構造で編成され、Outlook のフォルダー ビューに常に表示されるので、簡単に参照できます。 パブリック フォルダーは、メールに対応でき、配布グループのメンバーとして追加できます。 配布グループに送信されたメールは、アーカイブや後で参照できるように、自動的にパブリック フォルダーに追加されます。 パブリック フォルダーは、SharePoint Online サブスクリプションを所有していない場合に、ドキュメントを簡単に共有する方法として利用することもできます。  <br/> |
   
## <a name="which-collaboration-tool-to-use"></a>用途から見た共同作業ツールの比較
<a name="BKMK_SUMMARYOFCOLLABORATIONOPTIONS"> </a>

次の表では、さまざまな種類のグループを簡単に説明し、それらをさまざまなコラボレーション機能と共に使用する状況と方法について説明します。
  

||**Outlook のグループ**|**配布リスト**|**共有メールボックス**|**パブリック フォルダー**|
|:-----|:-----|:-----|:-----|:-----|
|**ユーザーのタイプ** <br/> |既に使用しているサービス (Outlook Web App、OneDrive for Business) に統合されたグループメッセージ、ファイル、および予定表に対してコラボレーションワークスペースを必要とするユーザー。  <br/> |共通の関心または特徴を持つ受信者のグループに電子メールを送信する必要があるユーザー。  <br/> |共有メールボックスは、組織内の複数のユーザーがメールボックスを監視してクエリに応答する責任を共有できるため、顧客のメールに関する質問を処理するのに便利な方法です。 お客様の質問により迅速な回答が得られ、関連するメールはすべて1つのメールボックスに保存されます。  <br/><br/> Delegates working on behalf of a virtual identity, such as support@contoso.com. Delgates can respond to email as that shared mailbox identity.  <br/> |With the proper permissions, everyone in your organization can access and search public folders. They are ideal for email archiving or for sharing documents.  <br/> |
|**理想的なグループ サイズ** <br/> |ANY  <br/> |大  <br/> |小さな  <br/> |大規模な  <br/> |
|**Access** <br/> |Exchange Online およびユーザー  <br/> |配布グループでは、メンバーを手動で追加する必要があります。 動的配布グループでは、メンバーはフィルター条件に基づいて追加されます。  <br/> |Users can be granted Full Access and/or Send As permissions. If granted Full Access permissions, users must also add the shared mailbox to their Outlook profile to access the shared mailbox.  <br/> |組織内のすべてのユーザーがアクセスできます  <br/> |
|**共有予定表** <br/> |はい  <br/> |いいえ  <br/> |○  <br/> |はい  <br/> |
|**メールはユーザーの個人用受信トレイに配信されるか?** <br/> |No. Users can subscribe to a group and then forward all Group messages to their inbox  <br/> |Yes. Email arrives in the inbox of all distribution group members.  <br/> |No. Email arrives in the Inbox of the shared mailbox.  <br/> |No. Email arrives in the public folder.  <br/> |
|**サポート対象のクライアント アプリケーション** <br/> | Outlook 2016  <br/>  Outlook 2013 (サブスクライブ後に転送)  <br/>  Outlook Web App  <br/>  Outlook 2010 (サブスクライブ後に転送)  <br/>  Outlook 2007 (サブスクライブ後に転送)  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> | Outlook 2016  <br/>  Outlook 2013  <br/>  Outlook Web App  <br/>  Outlook 2010  <br/>  Outlook 2007  <br/> |

  
## <a name="related-articles"></a>関連記事

[配布グループの管理](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)
    
[サイトメールボックスではなく Microsoft 365 グループを使用する](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)
    
[Microsoft 365 で共有メールボックスを作成する](create-a-shared-mailbox.md)
    
[Microsoft 365 および Exchange Online のパブリックフォルダー](https://technet.microsoft.com/library/jj200758%28v=exchg.150%29.aspx)
    

