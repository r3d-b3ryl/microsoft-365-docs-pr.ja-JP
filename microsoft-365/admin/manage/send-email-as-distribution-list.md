---
title: 配布リストとして電子メールを送信する
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: メールを配布リストとして送信Microsoft 365、メンバーがメッセージに返信すると、そのメールは配布リストから送信されたと思われる。
ms.openlocfilehash: c77455b5b990a9c35fc7e47ee81cc9ddef4d0a23
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392517"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="ed407-103">配布リストとして電子メールを送信する</span><span class="sxs-lookup"><span data-stu-id="ed407-103">Send email as a distribution list</span></span>

<span data-ttu-id="ed407-104">このMicrosoft 365、配布リストとして電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="ed407-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="ed407-105">配布リストのメンバーであるユーザーが配布リストに送信されたメッセージに返信すると、メールは個別のユーザーからではなく、配布リストからであることが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed407-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="ed407-106">このトピックでは、この操作を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ed407-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ed407-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="ed407-107">Before you begin</span></span>

<span data-ttu-id="ed407-108">これらの手順を実行する前に、Microsoft 365 配布リストに追加され、その配布リストに対する送信権限が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed407-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="ed407-109">**管理者**: [[Microsoft 365](../email/add-user-or-contact-to-distribution-list.md)ユーザーまたは連絡先をリストに追加する] および [メンバーが [Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)グループ トピックとして電子メールを送信するを許可する] の手順に従い、配布リストに正しいユーザーを追加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed407-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="ed407-110">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="ed407-110">Outlook on the web</span></span>

1. <span data-ttu-id="ed407-111">Outlook on the web を開き、受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed407-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="ed407-112">配布リストに送信されたメッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed407-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="ed407-113">[返信 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed407-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="ed407-114">メッセージの下部で、[より多くの表示] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed407-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="ed407-115">![[詳細] を選択し、[Show From] を選択します。](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="ed407-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="ed407-116">From アドレス (など) を右クリックし、[ `Ina@weewalter.me` 削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed407-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="ed407-117">![FROM エイリアスを削除する](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="ed407-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="ed407-118">次に、support@contoso.com などの配布リストを入力して、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ed407-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="ed407-119">次に配布リストから返信すると、そのアドレスが [From] リストにオプションとして **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ed407-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="ed407-120">![共有メールボックスのエイリアスが表示される](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="ed407-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="ed407-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="ed407-121">Outlook</span></span>

1. <span data-ttu-id="ed407-122">デスクトップ Outlookを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed407-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="ed407-123">新しいメールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed407-123">Compose a New Email.</span></span> <span data-ttu-id="ed407-124">[From] **フィールドをクリック** し、[その他の **メール アドレス] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed407-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="ed407-125">[From] フィールドが表示されない場合は、[オプション] に移動し、[フィールドの表示] セクションで **[From]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed407-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="ed407-126">グローバル アドレス **一覧から** 配布リスト アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed407-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="ed407-127">電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="ed407-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="ed407-128">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="ed407-128">Related content</span></span>

<span data-ttu-id="ed407-129">[セキュリティ グループを](../email/create-edit-or-delete-a-security-group.md)作成、編集、または削除するには、Microsoft 365 管理センター (記事)</span><span class="sxs-lookup"><span data-stu-id="ed407-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="ed407-130">[電子メールの共同作業](../email/email-collaboration.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="ed407-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
<span data-ttu-id="ed407-131">[配布グループにユーザーまたは連絡先を追加する](../email/add-user-or-contact-to-distribution-list.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="ed407-131">[Add a user or contact to a distribution group](../email/add-user-or-contact-to-distribution-list.md) (article)</span></span>