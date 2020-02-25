---
title: カスタマイズされたヘルプ デスク情報を Office 365 ヘルプ ウィンドウに追加する
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 9dd9b104-68f7-4d49-9a30-82561c7d79a3
description: 管理センターでカスタムのヘルプデスクカードを作成し、カスタマイズされたサポート連絡先情報を [ヘルプ] ウィンドウに追加します。
ms.openlocfilehash: af1000be1f8b26e79097f8b686aafc37da6e9366
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248083"
---
# <a name="add-customized-help-desk-info-to-the-office-365-help-pane"></a><span data-ttu-id="57976-103">カスタマイズされたヘルプ デスク情報を Office 365 ヘルプ ウィンドウに追加する</span><span class="sxs-lookup"><span data-stu-id="57976-103">Add customized help desk info to the Office 365 help pane</span></span>

<span data-ttu-id="57976-104">管理者は、カスタマイズした連絡先情報をヘルプウィンドウに追加することによって、ユーザーサポートを合理化できます。</span><span class="sxs-lookup"><span data-stu-id="57976-104">As an admin, you can streamline user support by adding customized contact information to the help pane.</span></span> <span data-ttu-id="57976-105">ヘルプが必要なユーザーは、ヘルプアイコンを使用して、組織のカスタムサポート連絡先情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="57976-105">Users in need of help will be able to access your organization's custom support contact info with the help icon.</span></span>
  
<span data-ttu-id="57976-106">カスタムヘルプデスクカードを作成するには、Office 365 用のグローバル管理者であり、Exchange Online のライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57976-106">To create a custom help desk card, you must be a global admin for Office 365 and have a license to Exchange Online.</span></span> <span data-ttu-id="57976-107">一般[法人向け Office 365 にライセンスを割り当てる](../manage/assign-licenses-to-users.md)方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57976-107">Learn how to [assign licenses in Office 365 for business](../manage/assign-licenses-to-users.md).</span></span>

> [!NOTE]
> <span data-ttu-id="57976-108">Microsoft からの技術的または課金に関するサポートを求めている管理者の場合は、「 [Office 365 for business サポートにお問い合わせ](../contact-support-for-business-products.md)ください。</span><span class="sxs-lookup"><span data-stu-id="57976-108">If you are an admin looking for technical or billing support from Microsoft, see [Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span> 

  
### <a name="create-the-custom-help-desk-card-in-the-admin-center"></a><span data-ttu-id="57976-109">管理センターでカスタムのヘルプデスクカードを作成する</span><span class="sxs-lookup"><span data-stu-id="57976-109">Create the custom help desk card in the admin center</span></span>
<span data-ttu-id="57976-110"><a name="BKMK_HelpDeskPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="57976-110"><a name="BKMK_HelpDeskPreview"> </a></span></span>

1. <span data-ttu-id="57976-111">管理センターで、**設定** > の**設定**に移動して、[**ヘルプデスク情報**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="57976-111">In the admin center, go to the **Settings** > **Settings** and choose **Help desk information** tab.</span></span>
    
2. <span data-ttu-id="57976-112">[**組織プロファイル**] タブで、[**カスタムアプリ起動ツールタイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57976-112">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="57976-113">[**ヘルプデスクの連絡先情報の追加**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="57976-113">Turn on the **Add your help desk contact information**.</span></span>
    
4. <span data-ttu-id="57976-114">管理者は、ユーザーに提供する連絡先情報の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="57976-114">As an admin, you decide what kind of contact information you want to give users.</span></span> <span data-ttu-id="57976-115">タイトルと1つ以上の形式の連絡先情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="57976-115">The title and at least one form of contact information are required.</span></span> <span data-ttu-id="57976-116">表示するものを選択し、適切な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="57976-116">Select what you want to display, and fill out the appropriate info.</span></span>
    
  - <span data-ttu-id="57976-117">**タイトル**: "Contoso help desk" や "ヘルプが必要ですか" などの目的を明確に示すタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="57976-117">**Title**: Enter a title that clearly indicates your intent, like "Contoso help desk" or "Need help?"</span></span>
    
  - <span data-ttu-id="57976-118">**電話**: ユーザーが発信する電話番号を入力して、組織のテクニカルサポートエージェントに連絡します。</span><span class="sxs-lookup"><span data-stu-id="57976-118">**Phone**: Enter the phone number users should call to talk to a tech support agent at your organization.</span></span> <span data-ttu-id="57976-119">呼び出しを完了するために必要なすべてのプレフィックスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="57976-119">Be sure to include any prefixes that may be needed to complete the call.</span></span>
    
  - <span data-ttu-id="57976-120">**Email**: サポート部門の電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="57976-120">**Email**: Enter the email address for your support department.</span></span>
    
  - <span data-ttu-id="57976-121">**URL**: サポート部門に、有用なツールとリソースを備えた内部またはパブリックの web サイトがある場合は、その名前と関連付けられた URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="57976-121">**URL**: If your support department has an internal or public website with helpful tools and resources, enter its name and the associated URL.</span></span>
    
5. <span data-ttu-id="57976-122">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57976-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="57976-123">新しいカスタマイズされたヘルプデスクカードを表示するには、サインアウトしてから再度サインインします。</span><span class="sxs-lookup"><span data-stu-id="57976-123">To see your new customized help desk card, sign out and back in again.</span></span> <span data-ttu-id="57976-124">サインインし直すとすぐに、カード上のリンクをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57976-124">We recommend you test the links on the card as soon as you sign back in.</span></span> <span data-ttu-id="57976-125">ユーザーは、次回サインインしたときにカードを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="57976-125">Your users will be able to see the card the next time they sign in.</span></span>
    

