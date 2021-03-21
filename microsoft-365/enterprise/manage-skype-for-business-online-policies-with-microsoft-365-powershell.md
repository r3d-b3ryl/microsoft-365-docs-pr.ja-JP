---
title: PowerShell を使用して Skype for Business Online を管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: '概要: PowerShell を使用して、ポリシーを使用して Skype for Business Online ユーザー アカウントのプロパティを管理します。'
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916704"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="67358-103">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="67358-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="67358-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="67358-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="67358-105">Skype for Business Online のユーザー アカウントの多くのプロパティを管理するには、それらを PowerShell for Microsoft 365 のポリシーのプロパティとして指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67358-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="67358-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="67358-106">Before you begin</span></span>

<span data-ttu-id="67358-107">次の手順にしたがってコマンドを実行するためのセットアップを行います (すでに終わっている場合はこれらの手順は省略可能です)。</span><span class="sxs-lookup"><span data-stu-id="67358-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="67358-108">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="67358-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="67358-109">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67358-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="67358-110">[Teams PowerShell モジュール](/microsoftteams/teams-powershell-install)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="67358-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="67358-111">Windows PowerShell コマンド プロンプトを開いて次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="67358-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="67358-112">ダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="67358-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="67358-113">ユーザー アカウント ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="67358-113">Manage user account policies</span></span>

<span data-ttu-id="67358-p102">多くの Skype for Business Online ユーザー アカウント プロパティは、ポリシーを使用して設定します。ポリシーは、1 人以上のユーザーに適用可能な設定の集合に過ぎません。ポリシーの構成方法については、FederationAndPICDefault ポリシーに関するサンプル コマンドを実行して確認できます。</span><span class="sxs-lookup"><span data-stu-id="67358-p102">Many Skype for Business Online user account properties are configured by using policies. Policies are simply collections of settings that can be applied to one or more users. To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="67358-117">これにより、次のように表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="67358-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="67358-118">このポリシー内の値は、ユーザーがフェデレーション ユーザーとの通信に関して実際にできることとできないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="67358-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="67358-119">たとえば、組織外部のユーザーと通信できるようにするためには、EnableOutsideAccess プロパティを True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67358-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="67358-120">このプロパティは、Microsoft 365 管理センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="67358-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="67358-121">代わりに、このプロパティはその他の選択内容に基づいて自動的に True または False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="67358-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="67358-122">関心のある他の 2 つのプロパティについては、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="67358-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="67358-123">**EnableFederationAccess** は、ユーザーがフェデレーション ドメインからのユーザーと通信できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="67358-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="67358-124">**EnablePublicCloudAccess** は、ユーザーが Windows Live ユーザーと通信できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="67358-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="67358-p104">つまり、ユーザー アカウント上のフェデレーション関連プロパティを直接変更したわけではなく (**Set-CsUser -EnableFederationAccess $True** など)、必要なプロパティ値が事前に構成された外部アクセス ポリシーをアカウントに割り当てただけです。ユーザーがフェデレーション ユーザーおよび Windows Live ユーザーと通信できるようにするには、ユーザー アカウントにこれらの種類の通信を可能にするポリシーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="67358-p104">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**). Instead, you assign an account an external access policy that has the desired property values preconfigured. If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="67358-128">特定のユーザーが組織外部のユーザーと通信できるかどうかを知りたい場合は、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67358-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="67358-129">そのユーザーに割り当てられている外部アクセス ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="67358-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="67358-130">そのポリシーで許可または禁止されている機能を特定します。</span><span class="sxs-lookup"><span data-stu-id="67358-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="67358-131">設定するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67358-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="67358-132">このコマンドでは、ユーザーに割り当てられたポリシーを探してから、そのポリシー内で有効または無効になっている機能を探します。</span><span class="sxs-lookup"><span data-stu-id="67358-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="67358-133">PowerShell を使用して Skype for Business Online ポリシーを管理するには、次のコマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67358-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="67358-134">[クライアント ポリシー](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="67358-134">[Client policy](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="67358-135">[会議ポリシー](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="67358-135">[Conferencing policy](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="67358-136">[モバイル ポリシー](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="67358-136">[Mobile policy](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="67358-137">[オンラインボイスメール ポリシー](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="67358-137">[Online Voicemail policy](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="67358-138">[音声ルーティング ポリシー](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="67358-138">[Voice Routing policy](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="67358-p105">Skype for Business Online ダイヤル プランは、名前以外はポリシーそのものです。「ダイヤル プラン」という名前は、Office Communications Server と Exchange との下位互換性を維持するために「ダイヤル ポリシー」の代わりに選択されたものです。</span><span class="sxs-lookup"><span data-stu-id="67358-p105">A Skype for Business Online dial plan is a policy in every respect except the name. The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="67358-141">たとえば、用途に使用可能なすべての音声ポリシーを調べるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67358-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="67358-p106">このコマンドは、使用可能なすべての音声ポリシーのリストを返します。ただし、すべてのポリシーをすべてのユーザーに割り当てられるとは限らない点に注意してください。これは、ライセンスや地理的な位置など、さまざまな制限によります (いわゆる「[使用場所](/previous-versions/azure/dn194136(v=azure.100))」のことです)。特定のユーザーに割り当てることが可能な外部アクセス ポリシーと会議ポリシーを知りたい場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67358-p106">That returns a list of all the voice policies available to you. Keep in mind, however, that not all policies can be assigned to all users. This is due to various restrictions involving licensing and geographic location. (The so-called "[usage location](/previous-versions/azure/dn194136(v=azure.100)).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="67358-p107">ApplicableTo パラメーターは、返すデータを、指定されたユーザー (Alex Darrow など) に割り当てることが可能なポリシーに限定します。ライセンスと利用場所の制限によっては、使用可能なすべてのポリシーの一部しか表示しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="67358-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="67358-148">場合によっては、ポリシーのプロパティは Microsoft 365 では使用されませんが、他のプロパティは Microsoft サポート担当者によってのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="67358-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="67358-p108">Skype for Business Online を使用している場合は、何らかのポリシーによってユーザーを管理する必要があります。有効なポリシーに関連するプロパティが空白の場合、当該ユーザーには、ユーザーごとのポリシーが割り当てられていない場合に自動的に適用されるグローバル ポリシーによって管理されていることを意味します。ユーザー アカウントではクライアント ポリシーが表示されていないため、グローバル ポリシーによって管理されています。グローバル クライアント ポリシーを設定するには次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67358-p108">With Skype for Business Online, users must be managed by a policy of some kind. If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy. Because we don't see a client policy listed for a user account, it is managed by the global policy. You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="67358-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="67358-153">See also</span></span>

[<span data-ttu-id="67358-154">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="67358-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="67358-155">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="67358-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="67358-156">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="67358-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)