---
title: Enterprise State Roaming を有効にする
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409118"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="9e290-103">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="9e290-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="9e290-104">[Enterprise状態ローミングを使用すると](/azure/active-directory/devices/enterprise-state-roaming-overview)、ユーザーとアプリケーションの設定データをクラウドに安全に同期できます。</span><span class="sxs-lookup"><span data-stu-id="9e290-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="9e290-105">つまり、どのデバイスにサインインしても、同Windowsエクスペリエンスが得されます。</span><span class="sxs-lookup"><span data-stu-id="9e290-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="9e290-106">たとえば、デバイスの 1 Microsoft マネージド デスクトップを新しいデバイスに置き換える場合、そのデバイスは最後のデバイスとまったく同じように見え、動作します。</span><span class="sxs-lookup"><span data-stu-id="9e290-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="9e290-107">Enterprise状態ローミングは、ユーザー用に構成できる Microsoft マネージド デスクトップ サービスのオプション機能であり、ユーザーの一部として含まれているか管理Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="9e290-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="9e290-108">状態ローミングEnterprise有効にするには、「デバイスの状態ローミングを有効にする[Enterprise」の手順に従Azure Active Directory。](/azure/active-directory/devices/enterprise-state-roaming-enable)</span><span class="sxs-lookup"><span data-stu-id="9e290-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="9e290-109">[状態ローミングEnterprise有効にした場合、デバイスのセットアップ中に選択した言語が優先言語リストによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9e290-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="9e290-110">ユーザーはこれを簡単に修正することができますが、最初は一貫性のないローカライズ エクスペリエンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e290-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="9e290-111">デバイスをEnterpriseする前に、ユーザーに適切な状態ローミングが必要かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9e290-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="9e290-112">データの使用を開始するMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="9e290-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="9e290-113">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="9e290-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="9e290-114">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="9e290-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="9e290-115">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e290-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="9e290-116">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="9e290-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="9e290-117">状態Enterpriseを有効にする (このトピック)</span><span class="sxs-lookup"><span data-stu-id="9e290-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="9e290-118">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9e290-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="9e290-119">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="9e290-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="9e290-120">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="9e290-120">Deploy apps</span></span>](deploy-apps.md)
