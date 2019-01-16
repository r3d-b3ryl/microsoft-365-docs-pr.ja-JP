---
title: Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 保護するために Microsoft 365 を有効にする方法を学ぶ 10 の Windows デバイスがローカルの AD に参加しています。
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869148"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="b020d-103">Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b020d-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="b020d-p101">組織は、Windows サーバーの Active Directory の設置型を使用している場合は、ローカルの認証を必要とする設置型のリソースへのアクセスを維持しながら、10 の Windows のデバイスを保護するために Microsoft 365 のビジネスを設定できます。Azure AD で 10 の Windows デバイスを登録して、Microsoft 365 のビジネスでのモバイル デバイス管理の登録に続いて、Azure Active directory、Active Directory を同期して設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b020d-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="b020d-106">Microsoft 365 のビジネスを管理するドメインに参加しているデバイスの設定します。</span><span class="sxs-lookup"><span data-stu-id="b020d-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="b020d-p102">オンプレミスの Active Directory に加え、Azure Active Directory が提供する機能からメリットを享受するのには、組織のドメインに参加しているデバイスを設定するには、**ハイブリッド Azure AD には、デバイスが参加している**を実装できます。これらは、オンプレミスの Active Directory と、Azure Active Directory の両方に参加しているデバイスです。ハイブリッド Azure AD が参加しているデバイスの保護し、Microsoft 365 ビジネスによって管理されていることができます。</span><span class="sxs-lookup"><span data-stu-id="b020d-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="b020d-110">ハイブリッド Azure の AD に参加して、Microsoft 365 ビジネスによって管理されている Windows 10 デバイスを作成するには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="b020d-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="b020d-111">Azure Active Directory に、ユーザー、グループ、およびローカルの Active Directory から連絡先を同期するには、ディレクトリ同期ウィザードと Azure Active ディレクトリの説明に従って接続[Office 365 のディレクトリ同期の設定](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)を実行します。</span><span class="sxs-lookup"><span data-stu-id="b020d-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b020d-112">手順は、正確にマイクロソフト 365 ビジネスでも同じです。</span><span class="sxs-lookup"><span data-stu-id="b020d-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="b020d-113">Azure AD に参加しているハイブリッドにする 10 の Windows のデバイスを有効にする 3 の手順を完了する前に、次の前提条件を満たしているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b020d-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="b020d-114">Azure AD の最新バージョンを実行して接続します。</span><span class="sxs-lookup"><span data-stu-id="b020d-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="b020d-p103">Azure AD 接続 Azure AD に参加しているハイブリッドにデバイスのすべてのコンピューター オブジェクトが同期します。コンピューター オブジェクトが特定の組織単位 (OU) に属しているし、これらの Ou は、Azure AD での同期に設定されているかどうかを確認する場合も同様に接続します。</span><span class="sxs-lookup"><span data-stu-id="b020d-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="b020d-117">既存ドメインに参加している Windows の 10、デバイスのハイブリッド Azure AD 参加 Intune (Microsoft 365 ビジネス) でモバイル デバイス管理のためを登録を登録します。</span><span class="sxs-lookup"><span data-stu-id="b020d-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="b020d-p104">[ハイブリッド Azure Active Directory が参加しているデバイスを構成する方法](https://go.microsoft.com/fwlink/p/?linkid=872870)のステップ バイ ステップの指示に従います。これは、オンプレミスの Active Directory の同期を有効にする 10 の Windows コンピューターを結合し、クラウドを可能にします。</span><span class="sxs-lookup"><span data-stu-id="b020d-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="b020d-p105">モバイル デバイス管理のための 10 の Windows デバイスを登録するために、手順については[10 の Windows Intune グループ ポリシーを使用してデバイスの登録](https://go.microsoft.com/fwlink/p/?linkid=872871)を参照してください。ポリシーを設定して、グループでは、ローカル コンピューター レベルまたは一括操作では、ドメイン コント ローラー サーバーで、このグループ ポリシー設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b020d-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

