---
title: モバイル デバイス管理インフラストラクチャの終了条件
description: Microsoft 365 エンタープライズには、Microsoft Intune を使用してモバイル デバイスの管理が含まれています。要件と前提条件を確認、Intune は、Azure Active Directory リソースを使用して設定、macOS、iOS、Android、および Windows の登録、デバイス、アプリケーションを展開、構成プロファイルを作成、コンプライアンス ・ ポリシーを使用および携帯用の条件付きのアクセスを有効にします。Microsoft 365 エンタープライズ ・ デバイスの管理です。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365 マニュアル、モバイル デバイスの管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869170"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="8a82e-105">モバイル デバイス管理インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="8a82e-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="8a82e-106">*Microsoft 365 エンタープライズの E3、E5 のバージョンに適用されます。*</span><span class="sxs-lookup"><span data-stu-id="8a82e-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8a82e-107">展開プロセスの次の段階移動する前に、構成がモバイル デバイス管理のインフラストラクチャについて次の要件を満たしているを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a82e-107">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="8a82e-108">デバイス向けの組織のルールを適用するために、Azure AD ユーザーとグループの作成を含めて Intune が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8a82e-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="8a82e-109">作成したポリシーをデバイスが受信できるように、Intune にデバイスを登録しました。</span><span class="sxs-lookup"><span data-stu-id="8a82e-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="8a82e-110">アプリはデバイスに追加されるので、ユーザーは Exchange Online や SharePoint Online など、組織の Microsoft 365 のクラウド サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8a82e-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="8a82e-111">機能と設定は、作成した Azure AD ユーザーとグループを使用してデバイスに構成および適用されます。これにはウイルス対策の有効化や特定アプリの制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a82e-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="8a82e-p102">デバイスでファイアウォールやパスワードの長さを要求するようにコンプライアンス ポリシーが設定されています。準拠していないデバイスの場合、条件付きアクセスによって組織のデータへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8a82e-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>

## <a name="next-phase"></a><span data-ttu-id="8a82e-114">次のフェーズ</span><span class="sxs-lookup"><span data-stu-id="8a82e-114">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="8a82e-115">Microsoft 365 エンタープライズのエンド ・ ツー ・ エンドの展開のプロセスで、次の段階は、[情報の保護](infoprotect-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a82e-115">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [information protection](infoprotect-infrastructure.md).</span></span> |
