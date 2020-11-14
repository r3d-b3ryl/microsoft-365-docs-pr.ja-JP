---
title: ゲストアカウントの前提条件
description: ゲストアカウントの構成ガイドラインとそれらを調整する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073226"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="05de6-104">ゲストアカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="05de6-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="05de6-105">Microsoft マネージドデスクトップでは、ゲストアカウントへのアクセスのために、Azure AD 組織で次の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="05de6-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="05de6-106">これらの設定は、[ **外部 id/外部コラボレーション** ] の下の [Azure portal](https://portal.azure.com)で調整できます。</span><span class="sxs-lookup"><span data-stu-id="05de6-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="05de6-107">**管理者および guest 招待元役割のユーザーは、** **[はい]** に設定することができます</span><span class="sxs-lookup"><span data-stu-id="05de6-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="05de6-108">[ **共同作業の制限** ] で、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="05de6-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="05de6-109">[すべての **ドメインに招待を送信できるようにする (最も包括的な)** ] を選択した場合は、その他の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="05de6-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="05de6-110">[指定した **ドメインへの招待を拒否** する] を選択した場合は、Microsoft.com が対象のドメインに一覧表示されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="05de6-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="05de6-111">指定した **ドメインへの招待を許可する (最も限定的な)** 場合は、Microsoft.com *が* 対象のドメインに一覧表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="05de6-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="05de6-112">これらの設定を操作する制限を設定する場合は、Azure Active Directory **モダン Workplace サービスアカウント** を除外してください。</span><span class="sxs-lookup"><span data-stu-id="05de6-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="05de6-113">たとえば、ゲストアカウントが Intune ポータルにアクセスできないようにする条件付きアクセスポリシーがある場合、 **モダン Workplace Service アカウント** グループをこのポリシーから除外します。</span><span class="sxs-lookup"><span data-stu-id="05de6-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

