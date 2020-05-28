---
title: 配布リストとしてメールを送信する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Microsoft 365 で配布リストとしてメールを送信する方法について説明します。
ms.openlocfilehash: a917e59bbac40846fa289a97465f6d6e065b87ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399592"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="38972-103">配布リストとしてメールを送信する</span><span class="sxs-lookup"><span data-stu-id="38972-103">Send email as a distribution list</span></span>

<span data-ttu-id="38972-104">Microsoft 365 では、電子メールを配布リストとして送信できます。</span><span class="sxs-lookup"><span data-stu-id="38972-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="38972-105">配布リストのメンバーであるユーザーが配布リストに送信されたメッセージに返信すると、メールは個別のユーザーからではなく、配布リストからであることが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38972-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="38972-106">このトピックでは、この操作を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="38972-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="38972-107">配布リストとしてメールを送信する</span><span class="sxs-lookup"><span data-stu-id="38972-107">Send email as a distribution list</span></span>

<span data-ttu-id="38972-108">これらの手順を実行する前に、Microsoft 365 配布リストにが追加されており、それに対する送信者アクセス許可が付与されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38972-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="38972-109">**管理者**: 「 [microsoft 365 のユーザーまたは連絡先をリストに追加](../email/add-user-or-contact-to-distribution-list.md)し、[メンバーが microsoft 365 のグループのトピックとして電子メールを送信できるように](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)し、配布リストに正しいユーザーを追加することを許可する」の手順に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38972-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="38972-110">Outlook on the web を開き、受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="38972-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="38972-111">配布リストに送信されたメッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="38972-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="38972-112">[**返信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38972-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="38972-113">メッセージの下部で、[**その他** \> **の表示元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38972-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="38972-114">![[詳細] を選択し、[表示] を選択します。](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="38972-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="38972-115">-などの差出人のアドレスを右クリックして、[ `Ina@weewalter.me` **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38972-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="38972-116">![FROM エイリアスを削除する](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="38972-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="38972-117">次に、support@contoso.com などの配布リストを入力して、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="38972-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="38972-118">次回、配布リストから返信するときに、そのアドレスが [**差出人**] リストにオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="38972-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="38972-119">![共有メールボックスのエイリアスが表示されます。](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="38972-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

