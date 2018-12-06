---
title: '手順 3: Office 365 のセキュリティ強化を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 (Office 365 ATP を含む) のセキュリティ強化について理解し、構成します。
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869525"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="0e8a1-103">手順 3: Office 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="0e8a1-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="0e8a1-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="0e8a1-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="0e8a1-105">Office 365 サブスクリプションとそのデータが、最初から悪意のある脅威から保護されているようにするには、「[セキュリティ強化のために Office 365 テナントを構成する](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)」を参照し、次の追加セキュリティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="0e8a1-106">Office 365 セキュリティ/コンプライアンス センターの脅威管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="0e8a1-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="0e8a1-107">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="0e8a1-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="0e8a1-108">SharePoint 管理センターでのテナント レベルでの共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="0e8a1-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="0e8a1-109">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="0e8a1-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="0e8a1-110">構成が完了したら、セキュリティ状態に関する情報を次のソースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="0e8a1-111">セキュリティ センターとコンプライアンス センターのダッシュボードとレポート</span><span class="sxs-lookup"><span data-stu-id="0e8a1-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="0e8a1-112">Office 365 セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="0e8a1-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="0e8a1-113">このページにアクセスするには、Office 365 テナント管理者としてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="0e8a1-114">Cloud App Security または Office 365 Cloud App Security を使用してセキュリティ イベントとセキュリティ活動を監視することもできます。詳細については、「[Office 365 Cloud App Security の概要](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="0e8a1-115">その他のセキュリティ機能として、Office 365 Advanced Threat Protection (ATP) があります。ATP は、次の処理により組織の共同作業のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="0e8a1-116">メールの添付ファイルやリンクを保護する。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="0e8a1-117">Exchange Online のメールと、SharePoint Online、OneDrive for Business、Microsoft Teams のドキュメントに対し、スプーフィング インテリジェンスとフィッシング対策機能を提供する</span><span class="sxs-lookup"><span data-stu-id="0e8a1-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="0e8a1-p101">Office 365 ATP は Microsoft 365 Enterprise E5 に含まれています。Microsoft 365 Enterprise E3 を使用している場合は、ATP の個別ライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="0e8a1-120">Office 365 ATP を有効にするには、「[SharePoint Online、OneDrive for Business、Microsoft Teams の Office 365 Advanced Threat Protection を有効にする](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="0e8a1-121">詳細については、「[SharePoint、OneDrive、マイクロソフトのチーム用の office 365 の分析ツール](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="0e8a1-123">テスト ラボ ガイド: Office 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="0e8a1-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="0e8a1-124">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0e8a1-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0e8a1-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="0e8a1-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="0e8a1-126">特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="0e8a1-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


