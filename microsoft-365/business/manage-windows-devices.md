---
title: Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365 を有効にして、ローカルの AD に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071552"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="df78d-103">Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="df78d-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="df78d-104">組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="df78d-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="df78d-105">これを設定するには、最初に Active Directory を Azure Active Directory と同期し、次に、Windows 10 デバイスを Azure AD に登録して、Microsoft 365 Business によるモバイルデバイス管理用に登録します。</span><span class="sxs-lookup"><span data-stu-id="df78d-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="df78d-106">Microsoft 365 Business で管理するドメイン参加済みデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="df78d-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="df78d-107">オンプレミスの Active Directory に加えて Azure Active Directory によって提供される機能からメリットを得るために、組織のドメインに参加しているデバイスを設定するには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="df78d-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="df78d-108">これらは、オンプレミスの Active Directory と Azure Active Directory の両方に参加しているデバイスです。</span><span class="sxs-lookup"><span data-stu-id="df78d-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="df78d-109">ハイブリッド Azure AD に参加しているデバイスは、Microsoft 365 Business で保護および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="df78d-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="df78d-110">Windows 10 デバイスをハイブリッド Azure AD に参加させ、Microsoft 365 Business で管理するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="df78d-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="df78d-111">ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active directory に同期するには、「 [Set up Directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の説明に従って、ディレクトリ同期ウィザードと Azure Active directory Connect を実行します。</span><span class="sxs-lookup"><span data-stu-id="df78d-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df78d-112">この手順は、Microsoft 365 Business の場合とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="df78d-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="df78d-113">手順3を実行して、Windows 10 デバイスがハイブリッド Azure AD に参加できるようにするには、次の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df78d-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="df78d-114">Azure AD connect の最新バージョンを実行していること。</span><span class="sxs-lookup"><span data-stu-id="df78d-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="df78d-115">Azure AD connect は、ハイブリッド Azure AD に参加させるデバイスのすべてのコンピューターオブジェクトを同期しています。</span><span class="sxs-lookup"><span data-stu-id="df78d-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="df78d-116">コンピューターオブジェクトが特定の組織単位 (OU) に属している場合は、それらの Ou が Azure AD connect の同期にも設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df78d-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="df78d-117">既存のドメインに参加している Windows 10 デバイスをハイブリッド Azure AD に登録し、Intune によるモバイルデバイス管理のために登録する (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="df78d-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="df78d-118">[ハイブリッド Azure Active Directory に参加しているデバイスを構成する方法](https://go.microsoft.com/fwlink/p/?linkid=872870)について、手順に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="df78d-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="df78d-119">これにより、オンプレミスの Active Directory に参加している Windows 10 台のコンピューターの同期を有効にして、クラウドの準備を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="df78d-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="df78d-120">モバイルデバイスの管理用に Windows 10 デバイスを登録するには、「[グループポリシーを使用して windows 10 デバイスを Intune に登録](https://go.microsoft.com/fwlink/p/?linkid=872871)する (手順については)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df78d-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="df78d-121">グループポリシーの設定は、ローカルコンピューターレベルまたは一括操作に対して行うことができ、ドメインコントローラーサーバー上でこのグループポリシー設定を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="df78d-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>