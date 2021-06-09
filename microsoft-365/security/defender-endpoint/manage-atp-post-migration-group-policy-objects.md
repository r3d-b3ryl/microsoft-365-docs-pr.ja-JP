---
title: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する
description: グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、PowerShell、Microsoft Defender for Endpoint、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 15902e02156c59ec4edaed94f4ba321094bd42ac
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843024"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="01b48-104">グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を管理する</span><span class="sxs-lookup"><span data-stu-id="01b48-104">Manage Microsoft Defender for Endpoint with Group Policy Objects</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01b48-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="01b48-105">**Applies to:**</span></span>
- [<span data-ttu-id="01b48-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01b48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01b48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01b48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="01b48-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="01b48-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01b48-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="01b48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="01b48-110">デバイス (エンドポイント[ともMicrosoft エンドポイント マネージャー)](/mem)に対する組織の脅威保護機能を管理するには、この機能を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01b48-110">We recommend using [Microsoft Endpoint Manager](/mem) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> <span data-ttu-id="01b48-111">エンドポイント マネージャーには、Microsoft Intuneと[](/mem/intune/fundamentals/what-is-intune)Microsoft Endpoint Configuration Manager[が含Microsoft Endpoint Configuration Manager。](/mem/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="01b48-111">Endpoint Manager includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).</span></span> <span data-ttu-id="01b48-112">**[詳細については、「エンドポイント マネージャー」 を参照してください](/mem/endpoint-manager-overview)**。</span><span class="sxs-lookup"><span data-stu-id="01b48-112">**[Learn more about Endpoint Manager](/mem/endpoint-manager-overview)**.</span></span> 

<span data-ttu-id="01b48-113">ドメイン サービスのグループ ポリシー オブジェクトをAzure Active Directory、Microsoft Defender for Endpoint のいくつかの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="01b48-113">You can use Group Policy Objects in Azure Active Directory Domain Services to manage some settings in Microsoft Defender for Endpoint.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a><span data-ttu-id="01b48-114">グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="01b48-114">Configure Microsoft Defender for Endpoint with Group Policy Objects</span></span>

<span data-ttu-id="01b48-115">次の表に、グループ ポリシー オブジェクトを使用して Microsoft Defender for Endpoint を構成するために実行できるさまざまなタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="01b48-115">The following table lists various tasks you can perform to configure Microsoft Defender for Endpoint with Group Policy Objects.</span></span>

|<span data-ttu-id="01b48-116">タスク</span><span class="sxs-lookup"><span data-stu-id="01b48-116">Task</span></span>  |<span data-ttu-id="01b48-117">追加情報</span><span class="sxs-lookup"><span data-stu-id="01b48-117">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="01b48-118">**ユーザー オブジェクトとコンピューター オブジェクトの設定を管理する**</span><span class="sxs-lookup"><span data-stu-id="01b48-118">**Manage settings for user and computer objects**</span></span> <br/><br/><span data-ttu-id="01b48-119">*組み込みのグループ ポリシー オブジェクトをカスタマイズするか、組織のニーズに合わせてカスタム グループ ポリシー オブジェクトと組織単位を作成します。*</span><span class="sxs-lookup"><span data-stu-id="01b48-119">*Customize built-in Group Policy Objects, or create custom Group Policy Objects and organizational units to suit your organizational needs.*</span></span>     |[<span data-ttu-id="01b48-120">ドメイン サービス管理ドメインAzure Active Directoryグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="01b48-120">Administer Group Policy in an Azure Active Directory Domain Services managed domain</span></span>](/azure/active-directory-domain-services/manage-group-policy)   |
|<span data-ttu-id="01b48-121">**構成Microsoft Defender ウイルス対策**</span><span class="sxs-lookup"><span data-stu-id="01b48-121">**Configure Microsoft Defender Antivirus**</span></span> <br/><br/><span data-ttu-id="01b48-122">*組織のデバイス&ポリシー設定、除外、修復、スケジュールされたスキャン (エンドポイントとも呼ばれます) などのウイルス対策機能を構成します。*</span><span class="sxs-lookup"><span data-stu-id="01b48-122">*Configure antivirus features & capabilities, including policy settings, exclusions, remediation, and scheduled scans on your organization's devices (also referred to as endpoints).*</span></span>   |[<span data-ttu-id="01b48-123">グループ ポリシー設定を使用して、グループ ポリシーの構成とMicrosoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="01b48-123">Use Group Policy settings to configure and manage Microsoft Defender Antivirus</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[<span data-ttu-id="01b48-124">グループ ポリシーを使用してクラウド配信の保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="01b48-124">Use Group Policy to enable cloud-delivered protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|<span data-ttu-id="01b48-125">**組織の攻撃表面の縮小ルールを管理する**</span><span class="sxs-lookup"><span data-stu-id="01b48-125">**Manage your organization's attack surface reduction rules**</span></span> <br/><br/><span data-ttu-id="01b48-126">*フォルダー内のファイルを除外するか、&デバイスに表示される通知通知にカスタム テキストを追加して、攻撃表面の縮小ルールをカスタマイズします。*</span><span class="sxs-lookup"><span data-stu-id="01b48-126">*Customize your attack surface reduction rules by excluding files & folders, or by adding custom text to notification alerts that appear on users' devices.*</span></span> |[<span data-ttu-id="01b48-127">グループ ポリシー オブジェクトを使用して攻撃表面の縮小ルールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="01b48-127">Customize attack surface reduction rules with Group Policy Objects</span></span>](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|<span data-ttu-id="01b48-128">**エクスプロイト保護の設定を管理する**</span><span class="sxs-lookup"><span data-stu-id="01b48-128">**Manage exploit protection settings**</span></span><br/><br/><span data-ttu-id="01b48-129">*エクスプロイト保護設定をカスタマイズし、構成ファイルをインポートしてから、グループ ポリシーを使用してその構成ファイルを展開できます。*</span><span class="sxs-lookup"><span data-stu-id="01b48-129">*You can customize your exploit protection settings, import a configuration file, and then use Group Policy to deploy that configuration file.*</span></span>  |[<span data-ttu-id="01b48-130">エクスプロイト保護の設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="01b48-130">Customize exploit protection settings</span></span>](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[<span data-ttu-id="01b48-131">エクスプロイト保護構成のインポート、エクスポート、展開</span><span class="sxs-lookup"><span data-stu-id="01b48-131">Import, export, and deploy exploit protection configurations</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[<span data-ttu-id="01b48-132">グループ ポリシーを使用して構成を配布する</span><span class="sxs-lookup"><span data-stu-id="01b48-132">Use Group Policy to distribute the configuration</span></span>](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|<span data-ttu-id="01b48-133">**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="01b48-133">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="01b48-134">*テスト環境で [ネットワーク保護のために](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。*</span><span class="sxs-lookup"><span data-stu-id="01b48-134">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="01b48-135">グループ ポリシーを使用してネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="01b48-135">Turn on network protection using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|<span data-ttu-id="01b48-136">**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する</span><span class="sxs-lookup"><span data-stu-id="01b48-136">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="01b48-137">*[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders) は、アンチランソイエムウェア保護とも呼ばれます。*</span><span class="sxs-lookup"><span data-stu-id="01b48-137">*[Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders) is also referred to as antiransomware protection.*</span></span>  |[<span data-ttu-id="01b48-138">グループ ポリシーを使用してフォルダー アクセスの制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="01b48-138">Enable controlled folder access using Group Policy</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|<span data-ttu-id="01b48-139">**インターネット上Microsoft Defender SmartScreen** 悪意のあるサイトやファイルから保護する方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="01b48-139">**Configure Microsoft Defender SmartScreen** to protect against malicious sites and files on the internet.</span></span>  |[<span data-ttu-id="01b48-140">グループ Microsoft Defender SmartScreenを使用して、グループ ポリシーとモバイル デバイス管理 (MDM) の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="01b48-140">Configure Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy</span></span>](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|<span data-ttu-id="01b48-141">**暗号化と暗号化BitLocker** を構成して、組織で実行されているデバイスの情報を保護Windows</span><span class="sxs-lookup"><span data-stu-id="01b48-141">**Configure encryption and BitLocker** to protect information on your organization's devices running Windows</span></span> |[<span data-ttu-id="01b48-142">BitLockerグループ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="01b48-142">BitLocker Group Policy settings</span></span>](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|<span data-ttu-id="01b48-143">**資格情報の盗難攻撃から** 保護するために Microsoft Defender Credential Guard を構成する</span><span class="sxs-lookup"><span data-stu-id="01b48-143">**Configure Microsoft Defender Credential Guard** to protect against credential theft attacks</span></span> |[<span data-ttu-id="01b48-144">グループ ポリシー Windows Defender Credential Guardしてグループ ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="01b48-144">Enable Windows Defender Credential Guard by using Group Policy</span></span>](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="01b48-145">サーバーを構成Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="01b48-145">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="01b48-146">まだ行っていない場合は **、Microsoft Defender セキュリティ センター** ( ) を構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報 [https://securitycenter.windows.com](https://securitycenter.windows.com) の表示を行います。</span><span class="sxs-lookup"><span data-stu-id="01b48-146">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="01b48-147">また、エンド ユーザーに表示される機能と機能を構成Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="01b48-147">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="01b48-148">アプリケーションのMicrosoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="01b48-148">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="01b48-149">エンドポイント保護: Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="01b48-149">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="01b48-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="01b48-150">Next steps</span></span>

- [<span data-ttu-id="01b48-151">アプリケーションの概要を脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="01b48-151">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="01b48-152">セキュリティ操作ダッシュボードMicrosoft Defender セキュリティ センターアクセスする</span><span class="sxs-lookup"><span data-stu-id="01b48-152">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="01b48-153">Intune を使用してエンドポイント用 Microsoft Defender を管理する</span><span class="sxs-lookup"><span data-stu-id="01b48-153">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
