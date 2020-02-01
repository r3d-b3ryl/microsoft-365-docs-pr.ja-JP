---
title: モバイルデバイス管理インフラストラクチャの終了条件
description: Microsoft 365 Enterprise には、Microsoft Intune を使用したモバイルデバイス管理が含まれます。 要件と前提条件を確認し、Azure Active Directory リソースを使用して Intune を設定し、iOS、macOS、Android、および Windows デバイスを登録し、アプリを展開し、構成プロファイルを作成し、コンプライアンスポリシーを使用して、モバイルの条件付きアクセスを有効にします。Microsoft 365 Enterprise を使用したデバイス管理。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600884"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="8ac03-105">モバイルデバイス管理インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="8ac03-105">Mobile device management infrastructure exit criteria</span></span>

![フェーズ 5: モバイル デバイス管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="8ac03-107">*これは、Microsoft 365 Enterprise の E3 および E5 バージョンに適用されます。*</span><span class="sxs-lookup"><span data-stu-id="8ac03-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8ac03-108">構成が、モバイルデバイス管理インフラストラクチャの次の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ac03-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="8ac03-109">Intune がセットアップされています。これにより、Azure Active Directory (Azure AD) ユーザーとグループを作成して、組織のデバイスに対するルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="8ac03-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="8ac03-110">作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。</span><span class="sxs-lookup"><span data-stu-id="8ac03-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="8ac03-111">アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8ac03-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="8ac03-112">機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ac03-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="8ac03-113">コンプライアンスポリシーは、デバイスでファイアウォールまたはパスワードの長さを要求するために配置されます。</span><span class="sxs-lookup"><span data-stu-id="8ac03-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="8ac03-114">デバイスが準拠していない場合、条件付きアクセスでは組織のデータへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8ac03-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="8ac03-115">結果と次の手順</span><span class="sxs-lookup"><span data-stu-id="8ac03-115">Results and next steps</span></span>

<span data-ttu-id="8ac03-116">デバイスは Intune に登録され、適切なポリシーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8ac03-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="8ac03-118">Microsoft 365 Enterprise のエンドツーエンドの展開のフェーズに従っている場合、次のフェーズは[情報保護](infoprotect-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ac03-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
