---
title: '手順 3: Microsoft 365 のセキュリティ強化を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 のセキュリティ強化を理解して、構成します。
ms.openlocfilehash: a1976a9305c40d721bd56a4b21b8a52552c1a9dc
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285082"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="68520-103">手順 3: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="68520-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="68520-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="68520-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="68520-105">Microsoft 365 サブスクリプションとそのデータが、悪意のある脅威から最初から保護されているようにするには、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="68520-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see Configure your Office 365 tenant for increased security and configure the following additional security:</span></span>

- [<span data-ttu-id="68520-106">脅威管理ポリシーの調整</span><span class="sxs-lookup"><span data-stu-id="68520-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="68520-107">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="68520-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="68520-108">SharePoint 管理センターでのテナント レベルでの共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="68520-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="68520-109">Azure Active Directory (Azure AD) の設定</span><span class="sxs-lookup"><span data-stu-id="68520-109">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="68520-110">構成が完了したら、セキュリティ状態に関する情報を次のソースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="68520-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="68520-111">Microsoft セキュリティ センターのダッシュボードとレポート</span><span class="sxs-lookup"><span data-stu-id="68520-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="68520-112">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="68520-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="68520-113">その他のセキュリティ機能として、[Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) があります。ATP は、次の処理により組織の共同作業のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="68520-113">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="68520-114">メールの[リンク](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)と[添付ファイル](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)を保護する。</span><span class="sxs-lookup"><span data-stu-id="68520-114">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="68520-115">Exchange Online のメールと、[SharePoint Online、OneDrive for Business、Microsoft Teams のファイル](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)に対し、スプーフィング インテリジェンスとフィッシング対策機能を提供する。</span><span class="sxs-lookup"><span data-stu-id="68520-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

<span data-ttu-id="68520-116">Office 365 ATP は、Microsoft 365 Enterprise E5 でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="68520-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="68520-118">テスト ラボ ガイド: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="68520-118">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="68520-119">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="68520-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="68520-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="68520-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="68520-121">特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="68520-121">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


