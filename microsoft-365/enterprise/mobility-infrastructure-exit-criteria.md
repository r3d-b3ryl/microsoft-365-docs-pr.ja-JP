---
title: モバイルデバイス管理インフラストラクチャの終了条件
description: microsoft 365 Enterprise には、microsoft Intune を使用したモバイルデバイス管理が含まれます。 要件と前提条件を確認し、Azure Active Directory リソースを使用して Intune を設定し、iOS、macOS、Android、および Windows デバイスを登録し、アプリを展開し、構成プロファイルを作成し、コンプライアンスポリシーを使用して、モバイルの条件付きアクセスを有効にします。Microsoft 365 Enterprise を使用したデバイス管理。
keywords: microsoft 365、microsoft 365 Enterprise、microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291234"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="e2fcc-105">モバイルデバイス管理インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="e2fcc-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="e2fcc-106">*これは、Microsoft 365 Enterprise の E3 および E5 バージョンに適用されます。*</span><span class="sxs-lookup"><span data-stu-id="e2fcc-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e2fcc-107">構成が、モバイルデバイス管理インフラストラクチャの次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="e2fcc-108">デバイス向けの組織のルールを適用するために、Azure AD ユーザーとグループの作成を含めて Intune が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="e2fcc-109">作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="e2fcc-110">アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="e2fcc-111">機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="e2fcc-p102">デバイスでファイアウォールやパスワードの長さを要求するようにコンプライアンス ポリシーが設定されています。準拠していないデバイスの場合、条件付きアクセスによって組織のデータへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="e2fcc-114">結果と次の手順</span><span class="sxs-lookup"><span data-stu-id="e2fcc-114">Results and next steps</span></span>

<span data-ttu-id="e2fcc-115">デバイスは Intune に登録され、適切なポリシーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="e2fcc-116">Microsoft 365 Enterprise のエンドツーエンドの展開のフェーズに従っている場合、次のフェーズは[情報保護](infoprotect-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2fcc-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
