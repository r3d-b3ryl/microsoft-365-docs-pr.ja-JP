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
ms.openlocfilehash: fcf023960679cf624f3ea7421ab92b1a450d2524
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400031"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="4f7b4-103">手順 3: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="4f7b4-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="4f7b4-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="4f7b4-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="4f7b4-105">Microsoft 365 サブスクリプションとそのデータが、悪意のある脅威から最初から保護されているようにするには、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="4f7b4-106">脅威管理ポリシーの調整</span><span class="sxs-lookup"><span data-stu-id="4f7b4-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="4f7b4-107">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="4f7b4-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="4f7b4-108">SharePoint 管理センターでのテナント レベルでの共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="4f7b4-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="4f7b4-109">Azure Active Directory (Azure AD) の設定</span><span class="sxs-lookup"><span data-stu-id="4f7b4-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="4f7b4-110">構成が完了したら、セキュリティ状態に関する情報を次のソースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="4f7b4-111">Microsoft セキュリティ センターのダッシュボードとレポート</span><span class="sxs-lookup"><span data-stu-id="4f7b4-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="4f7b4-112">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="4f7b4-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="4f7b4-113">その他のセキュリティ機能として、[Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) があります。ATP は、次の処理により組織の共同作業のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="4f7b4-114">メールの[リンク](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)と[添付ファイル](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)を保護する。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="4f7b4-115">Exchange Online のメールと、[SharePoint Online、OneDrive for Business、Microsoft Teams のファイル](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)に対し、スプーフィング インテリジェンスとフィッシング対策機能を提供する。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="4f7b4-116">Office 365 ATP は、Microsoft 365 Enterprise E5 でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4f7b4-118">テスト ラボ ガイド: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="4f7b4-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="4f7b4-119">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f7b4-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f7b4-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="4f7b4-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="4f7b4-121">[Windows 情報保護を構成する](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4f7b4-121">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|


