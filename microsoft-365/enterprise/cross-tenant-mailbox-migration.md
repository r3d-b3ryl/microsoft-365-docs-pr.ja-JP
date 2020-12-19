---
title: テナント間でのメールボックスの移行
description: Microsoft 365 または 365 テナント間でOffice移動する方法。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: f151f02af695eb54eaf8f4f97936f4985fc7f8c0
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719204"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="10617-103">テナント間メールボックスの移行 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="10617-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="10617-104">以前は、Exchange Online テナントが同じ Exchange Online サービス内の別のテナントにメールボックスを移動する必要がある場合、メールボックスをオンプレミスに完全にオフボードしてから、新しいテナントにオンボードする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="10617-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="10617-105">新しいテナント間メールボックス移行機能により、移行元テナントと移行先テナントの両方のテナント管理者は、オンプレミス システムで最小限のインフラストラクチャの依存関係を持つテナント間でメールボックスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="10617-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="10617-106">これにより、メールボックスをオフボードおよびオンボードする必要が削除されます。</span><span class="sxs-lookup"><span data-stu-id="10617-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="10617-107">一般に、合併または分割時には、ユーザーとコンテンツを新しいテナントに移動する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="10617-108">ターゲット テナント管理者が移動を実行すると、オンプレミスからクラウド オンボーディングへの移行と同様にプル移動と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="10617-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="10617-109">テナント間の Exchange メールボックスの移動はテナント管理者によって完全にセルフサービスされ、ユーザーを新しい組織に移行するために必要な大規模なワークフローにスクリプト化できる既知のインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="10617-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="10617-110">管理者は、メールボックスの移動管理役割を介して使用可能なコマンドレットを使用して、テナント間の移動 `New-MigrationBatch` を実行できます。</span><span class="sxs-lookup"><span data-stu-id="10617-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="10617-111">移動プロセスには、メールボックスの同期中および最終処理時のテナント承認チェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10617-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="10617-112">移行するユーザーは、移行先のテナント Exchange Online システムに MailUsers として存在し、テナント間の移動を有効にする特定の属性でマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="10617-113">ターゲット テナントで適切に設定されていないユーザーの移動は、システムによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="10617-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="10617-114">移動が完了すると、移動元システムメールボックスが MailUser に変換され、targetAddress (Exchange では ExternalEmailAddress として表示されます) に宛先テナントへのルーティング アドレスがスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="10617-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="10617-115">このプロセスは、従来の MailUser をソース テナントに残し、一期間の共同存在とメール ルーティングを可能にします。</span><span class="sxs-lookup"><span data-stu-id="10617-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="10617-116">ビジネス プロセスが許可されている場合、ソース テナントはソース MailUser を削除するか、メール連絡先に変換できます。</span><span class="sxs-lookup"><span data-stu-id="10617-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="10617-117">テナント間の Exchange メールボックスの移行は、ハイブリッドまたはクラウドのテナント、またはこの 2 つの組み合わせでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="10617-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="10617-118">この記事では、テナント間のメールボックス移動のプロセスについて説明し、コンテンツ移動のソーステナントとターゲット テナントを準備する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10617-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="10617-119">ソース テナントとターゲット テナントの準備</span><span class="sxs-lookup"><span data-stu-id="10617-119">Preparing source and target tenants</span></span>

<span data-ttu-id="10617-120">テナント間の Exchange メールボックス移行機能では、テナント間の移行に対する承認とスコープが必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="10617-121">Azure Enterprise アプリケーションと Key Vault ストレージ ソリューションを使用して、テナント管理者は、あるテナントから別のテナントへの Exchange Online メールボックス移行の承認とスコープの両方を管理できます。</span><span class="sxs-lookup"><span data-stu-id="10617-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="10617-122">テナント間のメールボックス移動は、テナントペア間の認証に使用される Azure Active Directory (Azure AD) アプリケーションを確立するための招待と同意モデルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="10617-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="10617-123">組織上の関係や移行エンドポイントなどの追加コンポーネントも必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="10617-124">このセクションには、ターゲット ディレクトリ内の MailUser ユーザー オブジェクトを準備するために必要な具体的な手順は含まれていますが、移行バッチを送信するサンプル コマンドも含めもありません。</span><span class="sxs-lookup"><span data-stu-id="10617-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="10617-125">この情報については [、「移行先のユーザー オブジェクトを準備する」](#prepare-target-user-objects-for-migration) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10617-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10617-126">前提条件</span><span class="sxs-lookup"><span data-stu-id="10617-126">Prerequisites</span></span>

<span data-ttu-id="10617-127">テナント間のメールボックス移動機能では [、Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) がテナント ペア固有の Azure アプリケーションを確立して、あるテナントから別のテナントへのメールボックスの移行を認証および承認するために使用される証明書/シークレットを安全に保存してアクセスする必要があります。テナント間で証明書/シークレットを共有するための要件は削除されます。</span><span class="sxs-lookup"><span data-stu-id="10617-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="10617-128">開始する前に、Azure Key Vault、メールボックス アプリケーションの移動、EXO 移行エンドポイント、EXO 組織の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="10617-129">通常、グローバル管理者には、すべての構成手順を実行する権限があります。</span><span class="sxs-lookup"><span data-stu-id="10617-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="10617-130">さらに、セットアップを実行する前に、ソース テナントのメールが有効なセキュリティ グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="10617-131">これらのグループは、移行元 (またはリソースと呼ばれる場合があります) テナントからターゲット テナントに移動できるメールボックスの一覧の範囲を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="10617-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="10617-132">これにより、移動元テナント管理者は、移動する必要がある特定のメールボックスセットを制限またはスコープ設定して、意図しないユーザーの移行を防止できます。</span><span class="sxs-lookup"><span data-stu-id="10617-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="10617-133">入れ子になったグループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10617-133">Nested groups are not supported.</span></span>

<span data-ttu-id="10617-134">また、Microsoft 365 テナント ID を取得するには、信頼できるパートナー企業 (メールボックスの移動先) と連絡を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="10617-135">このテナント ID は、[組織の関係] フィールドで使用 `DomainName` されます。</span><span class="sxs-lookup"><span data-stu-id="10617-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="10617-136">サブスクリプションのテナント ID を取得するには、Microsoft 365 管理センターにサインインし、次に移動します [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="10617-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="10617-137">テナント ID プロパティのコピー アイコンをクリックして、クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="10617-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="10617-138">プロセスのしくみを次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="メールボックス移行のためのテナントの準備。":::

<span data-ttu-id="10617-140">[このイメージのより大きなバージョンを参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="10617-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="10617-141">テナントを準備する</span><span class="sxs-lookup"><span data-stu-id="10617-141">Prepare tenants</span></span>

<span data-ttu-id="10617-142">セットアップ スクリプトを実行すると、大きなレベルで次の構成操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="10617-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="10617-143">ターゲット テナントを準備します。</span><span class="sxs-lookup"><span data-stu-id="10617-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="10617-144">既存の Azure リソース グループが指定されていない場合は、新しい Azure リソース グループが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="10617-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="10617-145">既存の Key Vault が指定されていない場合は、新しいキー コンテナーが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="10617-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="10617-146">新しいアクセス ポリシーが、Office 365 Exchange Online メールボックス移行アプリケーション (SCRIPT) 用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="10617-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="10617-147">シークレットを移行アプリケーション (SCRIPT) に保持するために、新しい証明書 (または指定されている場合は既存の証明書) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="10617-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="10617-148">新しい Azure AD アプリケーションが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="10617-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="10617-149">証明書/シークレットが移行アプリケーション (SCRIPT) にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="10617-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="10617-150">メールボックス移行のアクセス許可は、アプリケーション (SCRIPT) に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="10617-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="10617-151">展開スクリプトは、ターゲット管理者が自分のアプリケーション (SCRIPT) に同意するまで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="10617-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="10617-152">ターゲット テナント管理者は、アプリケーションに付与されたアクセス許可に同意します (MANUAL)。</span><span class="sxs-lookup"><span data-stu-id="10617-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="10617-153">組織上の関係は、ターゲット テナント (SCRIPT) に対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="10617-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="10617-154">移行エンドポイントが作成され、メールボックスがターゲット テナント (SCRIPT) にプルされます。</span><span class="sxs-lookup"><span data-stu-id="10617-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="10617-155">ソース テナントを準備します。</span><span class="sxs-lookup"><span data-stu-id="10617-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="10617-156">移行元テナント管理者は、ターゲット テナントからのメールボックス移行アプリケーションへの招待に同意します (MANUAL)。</span><span class="sxs-lookup"><span data-stu-id="10617-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="10617-157">移行元テナント管理者は、移行アプリケーション (MANUAL) によって移動が許可されているメールボックスの一覧を含むメールが有効なセキュリティ グループをテナントに作成します。</span><span class="sxs-lookup"><span data-stu-id="10617-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="10617-158">移動要求 (SCRIPT) を受け入れるには、OAuth 検証にメールボックス移行アプリケーションを使用する必要があるという組織上の関係がターゲット テナントに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="10617-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="10617-159">ターゲット テナント管理者向けステップ バイ ステップの手順</span><span class="sxs-lookup"><span data-stu-id="10617-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="10617-160">GitHub SetupCrossTenantRelationshipForTargetTenant.ps1から、ターゲット テナントのセットアップ用のスクリプトを [ダウンロードします](https://github.com/microsoft/cross-tenant/releases/tag/Preview)。</span><span class="sxs-lookup"><span data-stu-id="10617-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="10617-161">スクリプト (SetupCrossTenantRelationshipForTargetTenant.ps1) を、スクリプトを実行するコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="10617-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="10617-162">Exchange Online ターゲット テナントへのリモート PowerShell 接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="10617-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="10617-163">繰り返しますが、Azure Key Vault のストレージと証明書、メールボックス アプリケーションの移動、EXO 移行エンドポイント、EXO 組織の関係を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="10617-164">ファイル フォルダー ディレクトリをスクリプトの場所に変更するか、スクリプトがリモート PowerShell セッションの現在の場所に保存されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="10617-165">次のパラメーターと値を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="10617-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="10617-166">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10617-166">Parameter</span></span> | <span data-ttu-id="10617-167">値</span><span class="sxs-lookup"><span data-stu-id="10617-167">Value</span></span> | <span data-ttu-id="10617-168">必須またはオプション</span><span class="sxs-lookup"><span data-stu-id="10617-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="10617-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="10617-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="10617-170">ターゲット テナント ドメイン (contoso onmicrosoft.com \. など)。</span><span class="sxs-lookup"><span data-stu-id="10617-170">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="10617-171">必須</span><span class="sxs-lookup"><span data-stu-id="10617-171">Required</span></span> |
    | <span data-ttu-id="10617-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="10617-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="10617-173">fabrikam などのソース テナント \. ドメインonmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="10617-173">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="10617-174">必須</span><span class="sxs-lookup"><span data-stu-id="10617-174">Required</span></span> |
    | <span data-ttu-id="10617-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="10617-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="10617-176">ソース テナント管理者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="10617-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="10617-177">これは、移行先の管理者から送信されたメールボックス移行アプリケーションの使用に同意する移行元テナント管理者です。これは、アプリケーションの電子メールの招待を受け取る管理者です。</span><span class="sxs-lookup"><span data-stu-id="10617-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="10617-178">必須</span><span class="sxs-lookup"><span data-stu-id="10617-178">Required</span></span> |
    | <span data-ttu-id="10617-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="10617-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="10617-180">ソース テナント組織 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="10617-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="10617-181">必須</span><span class="sxs-lookup"><span data-stu-id="10617-181">Required</span></span> |
    | <span data-ttu-id="10617-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="10617-182">-SubscriptionId</span></span>                             | <span data-ttu-id="10617-183">リソースの作成に使用する Azure サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="10617-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="10617-184">必須</span><span class="sxs-lookup"><span data-stu-id="10617-184">Required</span></span> |
    | <span data-ttu-id="10617-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="10617-185">-ResourceGroup</span></span>                              | <span data-ttu-id="10617-186">Key Vault を含む、または含む Azure リソース グループ名。</span><span class="sxs-lookup"><span data-stu-id="10617-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="10617-187">必須</span><span class="sxs-lookup"><span data-stu-id="10617-187">Required</span></span> |
    | <span data-ttu-id="10617-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="10617-188">-KeyVaultName</span></span>                               | <span data-ttu-id="10617-189">メールボックス移行アプリケーションの証明書/シークレットを格納する Azure Key Vault インスタンス。</span><span class="sxs-lookup"><span data-stu-id="10617-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="10617-190">必須</span><span class="sxs-lookup"><span data-stu-id="10617-190">Required</span></span> |
    | <span data-ttu-id="10617-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="10617-191">-CertificateName</span></span>                            | <span data-ttu-id="10617-192">キー コンテナー内の証明書を生成または検索する場合の証明書名。</span><span class="sxs-lookup"><span data-stu-id="10617-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="10617-193">必須</span><span class="sxs-lookup"><span data-stu-id="10617-193">Required</span></span> |
    | <span data-ttu-id="10617-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="10617-194">-CertificateSubject</span></span>                         | <span data-ttu-id="10617-195">AZURE Key Vault 証明書のサブジェクト名 (CN=contoso_fabrikam など)。</span><span class="sxs-lookup"><span data-stu-id="10617-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="10617-196">必須</span><span class="sxs-lookup"><span data-stu-id="10617-196">Required</span></span> |
    | <span data-ttu-id="10617-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="10617-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="10617-198">既に作成されている場合に使用するメール移行アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="10617-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="10617-199">オプション</span><span class="sxs-lookup"><span data-stu-id="10617-199">Optional</span></span> |
    | <span data-ttu-id="10617-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="10617-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="10617-201">Exchange や MSGraph (メールボックスを移動するための Exchange、このアプリケーションを使用してリソース テナントに同意リンクへの招待を送信するための MSGraph) など、メールボックス移行アプリケーションに与える必要があるアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="10617-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="10617-202">必須</span><span class="sxs-lookup"><span data-stu-id="10617-202">Required</span></span> |
    | <span data-ttu-id="10617-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="10617-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="10617-204">移行元テナント管理者に同意リンクの招待状を送信するために使用する、移行用に作成されたアプリケーションを使用するパラメーター。指定しない場合、ターゲット管理者の資格情報で Azure 招待マネージャーに接続し、ターゲット管理者として招待を送信するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10617-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="10617-205">オプション</span><span class="sxs-lookup"><span data-stu-id="10617-205">Optional</span></span> |
    | <span data-ttu-id="10617-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="10617-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="10617-207">Key Vault の監査ログが格納されるストレージ アカウント。</span><span class="sxs-lookup"><span data-stu-id="10617-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="10617-208">オプション</span><span class="sxs-lookup"><span data-stu-id="10617-208">Optional</span></span> |
    | <span data-ttu-id="10617-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="10617-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="10617-210">Key Vault 監査ログを格納するためのストレージ アカウントを含むリソース グループ。</span><span class="sxs-lookup"><span data-stu-id="10617-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="10617-211">オプション</span><span class="sxs-lookup"><span data-stu-id="10617-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="10617-212">スクリプトを実行する前に、Azure AD PowerShell モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="10617-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="10617-213">インストール手順については ![ 、 ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10617-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="10617-214">スクリプトは一時停止し、このプロセス中に作成された Exchange メールボックス移行アプリケーションに同意するか、同意を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10617-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="10617-215">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-215">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="10617-216">URL はリモート PowerShell セッションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="10617-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="10617-217">テナントの同意のために提供されたリンクをコピーし、Web ブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="10617-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="10617-218">グローバル管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="10617-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="10617-219">次の画面が表示された場合は、[承諾] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="10617-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[アクセス許可を受け入れる] ダイアログ ボックス":::

9. <span data-ttu-id="10617-221">リモート PowerShell セッションに戻り、Enter キーを押して続行します。</span><span class="sxs-lookup"><span data-stu-id="10617-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="10617-222">スクリプトは、残りのセットアップ オブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="10617-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="10617-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="10617-224">これで、ターゲット管理者のセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="10617-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="10617-225">ソース テナント管理者の詳しい手順</span><span class="sxs-lookup"><span data-stu-id="10617-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="10617-226">セットアップ中に、ターゲット管理者によって指定された -ResourceTenantAdminEmail としてメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="10617-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="10617-227">ターゲット テナントからメールへの招待を検索し、[開始] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="10617-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="招待されたダイアログ ボックス":::

2. <span data-ttu-id="10617-229">[承諾 **] を選択** して招待を承諾します。</span><span class="sxs-lookup"><span data-stu-id="10617-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="アクセス許可を受け入れるダイアログ ボックス":::

   > [!NOTE]
   > <span data-ttu-id="10617-231">このメールが届かできない場合、または見つからない場合は、ターゲットテナント管理者に直接 URL が提供されます。この URL を指定すると、招待を承諾できます。</span><span class="sxs-lookup"><span data-stu-id="10617-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="10617-232">URL は、ターゲット テナント管理者のリモート PowerShell セッションのトランスクリプト内に含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="10617-233">Microsoft 365 管理センターまたはリモート PowerShell セッションで、1 つ以上のメールが有効なセキュリティ グループを作成し、移動元テナントからターゲット テナントに移動 (プル) するためにターゲット テナントが許可するメールボックスの一覧を制御します。</span><span class="sxs-lookup"><span data-stu-id="10617-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="10617-234">このグループを事前に設定する必要はありますが、セットアップ手順 (スクリプト) を実行するには、少なくとも 1 つのグループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="10617-235">ネスト グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10617-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="10617-236">GitHub リポジトリSetupCrossTenantRelationshipForTargetResource.ps1ソース テナントのセットアップ用の次のスクリプトをダウンロードします [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 。</span><span class="sxs-lookup"><span data-stu-id="10617-236">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="10617-237">Exchange 管理者のアクセス許可を使用して、ソース テナントへのリモート PowerShell 接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="10617-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="10617-238">Azure アプリケーションの作成プロセスのため、グローバル管理者のアクセス許可はソース テナントを構成する必要はありません。ターゲット テナントのみを構成します。</span><span class="sxs-lookup"><span data-stu-id="10617-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="10617-239">ディレクトリをスクリプトの場所に変更するか、スクリプトがリモート PowerShell セッションの現在の場所に保存されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="10617-240">次の必須パラメーターと値を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="10617-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="10617-241">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10617-241">Parameter</span></span> | <span data-ttu-id="10617-242">値</span><span class="sxs-lookup"><span data-stu-id="10617-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="10617-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="10617-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="10617-244">移行対象の ID/メールボックスのソース テナントによって作成された、メールが有効なセキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="10617-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="10617-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="10617-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="10617-246">fabrikam などのソース テナント \. ドメインonmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="10617-246">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="10617-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="10617-247">-ApplicationId</span></span> | <span data-ttu-id="10617-248">移行に使用されるアプリケーションの Azure アプリケーション ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="10617-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="10617-249">Azure portal (Azure AD、エンタープライズ アプリケーション、アプリ名、アプリケーション ID) 経由で利用できるアプリケーション ID、または招待メールに含まれているアプリケーション ID。</span><span class="sxs-lookup"><span data-stu-id="10617-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="10617-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="10617-250">-TargetTenantDomain</span></span> | <span data-ttu-id="10617-251">ターゲット テナントドメイン名 (contoso onmicrosoft.com \. など)。</span><span class="sxs-lookup"><span data-stu-id="10617-251">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="10617-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="10617-252">-TargetTenantId</span></span> | <span data-ttu-id="10617-253">ターゲット テナントのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="10617-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="10617-254">たとえば、Azure ADテナント ID は contoso onmicrosoft.com \. です。</span><span class="sxs-lookup"><span data-stu-id="10617-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="10617-255">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="10617-256">これで、ソース管理者のセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="10617-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="10617-257">セットアップを確認する</span><span class="sxs-lookup"><span data-stu-id="10617-257">Verify setup</span></span>

<span data-ttu-id="10617-258">移行元テナントと移行先テナントの両方の組織上の関係と、ターゲット内の移行エンドポイントが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="10617-259">ターゲット テナント</span><span class="sxs-lookup"><span data-stu-id="10617-259">Target tenant</span></span>

<span data-ttu-id="10617-260">**組織の関係**</span><span class="sxs-lookup"><span data-stu-id="10617-260">**Organization relationship**</span></span>

<span data-ttu-id="10617-261">組織の関係オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="10617-262">次に例を示します：</span><span class="sxs-lookup"><span data-stu-id="10617-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="10617-263">**移行エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="10617-263">**Migration endpoint**</span></span>

<span data-ttu-id="10617-264">移行エンドポイント オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="10617-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="10617-266">ソース テナント</span><span class="sxs-lookup"><span data-stu-id="10617-266">Source tenant</span></span>

<span data-ttu-id="10617-267">**組織の関係**</span><span class="sxs-lookup"><span data-stu-id="10617-267">**Organization relationship**</span></span>

<span data-ttu-id="10617-268">組織の関係オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="10617-269">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="10617-270">メールボックスを元のソースに戻す</span><span class="sxs-lookup"><span data-stu-id="10617-270">Move mailboxes back to the original source</span></span>

<span data-ttu-id="10617-271">メールボックスを元のソース テナントに戻す必要がある場合は、新しいソース テナントと新しいターゲット テナントの両方で同じ手順とスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-271">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="10617-272">既存の Organization Relationship オブジェクトは更新または追加され、再作成されません。</span><span class="sxs-lookup"><span data-stu-id="10617-272">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="10617-273">移行のターゲット ユーザー オブジェクトを準備する</span><span class="sxs-lookup"><span data-stu-id="10617-273">Prepare target user objects for migration</span></span>

<span data-ttu-id="10617-274">テナント間の移動を有効にするには、移行先のテナントと Exchange Online システム (MailUsers として) に特定の属性がマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-274">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="10617-275">ターゲット テナントで適切に設定されていないユーザーの移動は、システムによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="10617-275">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="10617-276">次のセクションでは、ターゲット テナントの MailUser オブジェクトの要件について詳しい説明を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-276">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="10617-277">前提条件</span><span class="sxs-lookup"><span data-stu-id="10617-277">Prerequisites</span></span>
  
<span data-ttu-id="10617-278">次のオブジェクトと属性がターゲット組織で設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-278">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="10617-279">移動元の組織から移動するメールボックスの場合は、移動先の組織で MailUser オブジェクトを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-279">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="10617-280">移動先 MailUser には、移動元のメールボックスから次の属性を設定するか、新しいユーザー オブジェクトで割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-280">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="10617-281">ExchangeGUID (ソースからターゲットへの直接フロー) – メールボックス GUID が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-281">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="10617-282">移動先オブジェクトに存在しない場合、移動プロセスは続行できません。</span><span class="sxs-lookup"><span data-stu-id="10617-282">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="10617-283">ArchiveGUID (ソースからターゲットへの直接フロー) – アーカイブ GUID は一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-283">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="10617-284">移動先オブジェクトに存在しない場合、移動プロセスは続行できません。</span><span class="sxs-lookup"><span data-stu-id="10617-284">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="10617-285">(これは、移動元メールボックスがアーカイブが有効な場合にのみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="10617-285">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="10617-286">LegacyExchangeDN (proxyAddress、"x500: <LegacyExchangeDN> ") としてのフロー- LegacyExchangeDN は、ターゲット MailUser に x500: proxyAddress として存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-286">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="10617-287">移動先オブジェクトに存在しない場合、移動プロセスは続行できません。</span><span class="sxs-lookup"><span data-stu-id="10617-287">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="10617-288">UserPrincipalName – UPN は、ユーザーの新しい ID または対象の会社 (たとえば、user@northwindtraders.onmicrosoft.com) に合わせて配置されます。</span><span class="sxs-lookup"><span data-stu-id="10617-288">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="10617-289">プライマリ SMTPAddress – プライマリ SMTP アドレスは、ユーザーの新しい会社に合わせて調整されます (たとえば、user@northwind.com)。</span><span class="sxs-lookup"><span data-stu-id="10617-289">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="10617-290">TargetAddress/ExternalEmailAddress – MailUser は、ソース テナントでホストされているユーザーの現在のメールボックスを参照します (たとえば、user@contoso.onmicrosoft.com)。</span><span class="sxs-lookup"><span data-stu-id="10617-290">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="10617-291">この値を割り当てる場合は、PrimarySMTPAddress を割り当て中または割り当て中か、この値によって PrimarySMTPAddress が設定され、移動エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10617-291">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="10617-292">ソース メールボックスから移動先 MailUser に従来の smtp プロキシ アドレスを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="10617-292">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="10617-293">たとえば、テナント オブジェクトcontoso.com MEU に対するfabrikam.onmicrosoft.com保持することはできません。</span><span class="sxs-lookup"><span data-stu-id="10617-293">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="10617-294">ドメインは、1 つの Azure ADまたは Exchange Online テナントにのみ関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="10617-294">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="10617-295">ターゲット MailUser オブジェクトの例:</span><span class="sxs-lookup"><span data-stu-id="10617-295">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="10617-296">属性</span><span class="sxs-lookup"><span data-stu-id="10617-296">Attribute</span></span>             | <span data-ttu-id="10617-297">値</span><span class="sxs-lookup"><span data-stu-id="10617-297">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="10617-298">エイリアス</span><span class="sxs-lookup"><span data-stu-id="10617-298">Alias</span></span>                 | <span data-ttu-id="10617-299">Laran</span><span class="sxs-lookup"><span data-stu-id="10617-299">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="10617-300">RecipientType</span><span class="sxs-lookup"><span data-stu-id="10617-300">RecipientType</span></span>         | <span data-ttu-id="10617-301">MailUser</span><span class="sxs-lookup"><span data-stu-id="10617-301">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="10617-302">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="10617-302">RecipientTypeDetails</span></span>  | <span data-ttu-id="10617-303">MailUser</span><span class="sxs-lookup"><span data-stu-id="10617-303">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="10617-304">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="10617-304">UserPrincipalName</span></span>     | <span data-ttu-id="10617-305">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="10617-305">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="10617-306">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="10617-306">PrimarySmtpAddress</span></span>    | <span data-ttu-id="10617-307">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="10617-307">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="10617-308">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="10617-308">ExternalEmailAddress</span></span>  | <span data-ttu-id="10617-309">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="10617-309">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="10617-310">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="10617-310">ExchangeGuid</span></span>          | <span data-ttu-id="10617-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="10617-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="10617-312">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="10617-312">LegacyExchangeDN</span></span>      | <span data-ttu-id="10617-313">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="10617-313">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="10617-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="10617-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="10617-315">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="10617-315">EmailAddresses</span></span>        | <span data-ttu-id="10617-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="10617-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="10617-317">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="10617-317">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="10617-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="10617-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="10617-319">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="10617-319">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="10617-320">ソース **メールボックス オブジェクト** の例:</span><span class="sxs-lookup"><span data-stu-id="10617-320">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="10617-321">属性</span><span class="sxs-lookup"><span data-stu-id="10617-321">Attribute</span></span>             | <span data-ttu-id="10617-322">値</span><span class="sxs-lookup"><span data-stu-id="10617-322">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="10617-323">エイリアス</span><span class="sxs-lookup"><span data-stu-id="10617-323">Alias</span></span>                 | <span data-ttu-id="10617-324">Laran</span><span class="sxs-lookup"><span data-stu-id="10617-324">LaraN</span></span>                                                                    |
     | <span data-ttu-id="10617-325">RecipientType</span><span class="sxs-lookup"><span data-stu-id="10617-325">RecipientType</span></span>         | <span data-ttu-id="10617-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="10617-326">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="10617-327">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="10617-327">RecipientTypeDetails</span></span>  | <span data-ttu-id="10617-328">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="10617-328">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="10617-329">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="10617-329">UserPrincipalName</span></span>     | <span data-ttu-id="10617-330">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="10617-330">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="10617-331">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="10617-331">PrimarySmtpAddress</span></span>    | <span data-ttu-id="10617-332">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10617-332">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="10617-333">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="10617-333">ExchangeGuid</span></span>          | <span data-ttu-id="10617-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="10617-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="10617-335">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="10617-335">LegacyExchangeDN</span></span>      | <span data-ttu-id="10617-336">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="10617-336">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="10617-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="10617-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="10617-338">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="10617-338">EmailAddresses</span></span>        | <span data-ttu-id="10617-339">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="10617-339">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="10617-340">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10617-340">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="10617-341">追加の属性は、既に Exchange ハイブリッド 書き戻しに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10617-341">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="10617-342">含まれていない場合は、含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-342">If not, they should be included.</span></span> 
   - <span data-ttu-id="10617-343">msExchBlockedSendersHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。</span><span class="sxs-lookup"><span data-stu-id="10617-343">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="10617-344">msExchSafeRecipientsHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。</span><span class="sxs-lookup"><span data-stu-id="10617-344">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="10617-345">msExchSafeSendersHash – クライアントからオンプレミスの Active Directory にオンラインの安全な送信者データとブロックする差出人データを書き戻します。</span><span class="sxs-lookup"><span data-stu-id="10617-345">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="10617-346">移動元メールボックスが訴訟ホールドの対象であり、移動元メールボックスの回復可能なアイテムのサイズがデータベースの既定値 (30 GB) より大きい場合、移動先のクォータがソース メールボックスのサイズより小さいので、移動は続行されません。</span><span class="sxs-lookup"><span data-stu-id="10617-346">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="10617-347">ターゲット MailUser オブジェクトを更新して、ELC メールボックス フラグをソース環境からターゲットに移行できます。これにより、ターゲット システムは MailUser のクォータを 100 GB に拡張し、ターゲットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="10617-347">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="10617-348">これらの手順は、Azure AD Connect を実行しているハイブリッド ID でのみ機能します。ELC フラグをスタンプするコマンドはテナント管理者に公開されません。</span><span class="sxs-lookup"><span data-stu-id="10617-348">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="10617-349">サンプル – 現在、保証なし</span><span class="sxs-lookup"><span data-stu-id="10617-349">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="10617-350">このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory (ADUser オブジェクトにスタンプを付けます) の両方への接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="10617-350">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="10617-351">ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="10617-351">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="10617-352">これにより、宛先アカウントの削除のサイズが 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="10617-352">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="10617-353">非ハイブリッド ターゲット テナントは、次のコマンドを実行して MailUser オブジェクトの訴訟ホールドを有効にし、クォータを 100 GB に増やして、移行前に MailUsers の [回復可能なアイテム] フォルダーのクォータを変更できます。 `Set-MailUser -EnableLitigationHoldForMigration $TRUE`</span><span class="sxs-lookup"><span data-stu-id="10617-353">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="10617-354">これはハイブリッドのテナントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="10617-354">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="10617-355">ターゲット組織のユーザーには、組織に適用可能な適切な Exchange Online サブスクリプションのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-355">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="10617-356">メールボックスの移動の前にライセンスを適用できますが、ターゲット MailUser が ExchangeGUID とプロキシ アドレスで適切にセットアップされた後にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="10617-356">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="10617-357">ExchangeGUID を適用する前にライセンスを適用すると、ターゲット組織で新しいメールボックスがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="10617-357">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="10617-358">Mailbox オブジェクトまたは MailUser オブジェクトにライセンスを適用すると、すべての SMTP タイプの proxyAddresses がスクラブされ、確認済みのドメインだけが Exchange EmailAddresses 配列に含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-358">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="10617-359">移動先の MailUser に、ソース ExchangeGuid と一致しない以前の ExchangeGuid が存在しなかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-359">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="10617-360">これは、ターゲット MEU が以前に Exchange Online のライセンスを取得し、メールボックスをプロビジョニングした場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10617-360">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="10617-361">ターゲット MailUser が以前に ExchangeGuid に対してライセンスを付与されている場合、またはソース ExchangeGuid と一致しない ExchangeGuid を持っていた場合は、クラウド MEU のクリーンアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-361">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="10617-362">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="10617-362">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="10617-363">このプロセスは取り返しできません。</span><span class="sxs-lookup"><span data-stu-id="10617-363">This process is irreversible.</span></span> <span data-ttu-id="10617-364">オブジェクトに softDeleted メールボックスがある場合、この時点以降は復元できません。</span><span class="sxs-lookup"><span data-stu-id="10617-364">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="10617-365">ただし、クリアすると、正しい ExchangeGuid をターゲット オブジェクトに同期できます。MRS は、移動元メールボックスを新しく作成したターゲット メールボックスに接続します。</span><span class="sxs-lookup"><span data-stu-id="10617-365">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="10617-366">(新しいパラメーターに関する EHLO ブログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10617-366">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="10617-367">このコマンドを使用して、以前メールボックスだったオブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="10617-367">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```

    <span data-ttu-id="10617-368">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-368">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="10617-369">このコマンドを使用して、回復可能な削除によって削除されたメールボックスをクリアします。</span><span class="sxs-lookup"><span data-stu-id="10617-369">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="10617-370">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-370">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="10617-371">メールボックスの移行を実行する</span><span class="sxs-lookup"><span data-stu-id="10617-371">Perform mailbox migrations</span></span>

<span data-ttu-id="10617-372">テナント間の Exchange メールボックスの移行は、移行先のテナントから開始された移行バッチとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="10617-372">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="10617-373">これは、オンプレミスの Exchange から Microsoft 365 に移行する場合の移行バッチの動作と似ています。</span><span class="sxs-lookup"><span data-stu-id="10617-373">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="10617-374">移行バッチを作成する</span><span class="sxs-lookup"><span data-stu-id="10617-374">Create Migration batches</span></span>

<span data-ttu-id="10617-375">移動を開始する移行バッチ コマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-375">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="10617-376">CSV ファイルの電子メール アドレスは、ソース テナントではなく、ターゲット テナントで指定されたアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-376">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="10617-377">移行バッチの送信は、テナント間オプションを選択するときに、新しい Exchange 管理センターからサポートされます。</span><span class="sxs-lookup"><span data-stu-id="10617-377">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="10617-378">オンプレミスの MailUsers を更新する</span><span class="sxs-lookup"><span data-stu-id="10617-378">Update on-premises MailUsers</span></span>

<span data-ttu-id="10617-379">メールボックスがソースからターゲットに移動したら、オンプレミスのメール ユーザー (ソースとターゲットの両方) が新しい targetAddress で更新される必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-379">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="10617-380">この例では、移動で使用される targetDeliveryDomain が **contoso.onmicrosoft.com。**</span><span class="sxs-lookup"><span data-stu-id="10617-380">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="10617-381">この targetAddress でメール ユーザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="10617-381">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="10617-382">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="10617-382">Frequently asked questions</span></span>

<span data-ttu-id="10617-383">**移行後にオンプレミスのソースで RemoteMailboxes を更新する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="10617-383">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="10617-384">はい。移行元のテナント メールボックスがターゲット テナントに移動するときに、移動元のオンプレミス ユーザーの targetAddress (RemoteRoutingAddress/ExternalEmailAddress) を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-384">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="10617-385">メール ルーティングは、異なる targetAddresses を持つ複数のメール ユーザー間の紹介に従う可能性があります。メール ユーザーの空き時間情報の参照はメールボックス ユーザーの場所をターゲットとする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-385">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="10617-386">空き時間情報の参照は、複数のリダイレクトを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-386">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="10617-387">**Teams チャット フォルダーのコンテンツはテナント間で移行されますか?**</span><span class="sxs-lookup"><span data-stu-id="10617-387">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="10617-388">いいえ。Teams チャット フォルダーのコンテンツはテナント間を移行されません。</span><span class="sxs-lookup"><span data-stu-id="10617-388">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="10617-389">**オンボーディングとオフボーディングの移動ではなく、テナント間の移動である移動を確認するにはどうすれば良いでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="10617-389">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="10617-390">パラメーターを使用 `-flags` します。</span><span class="sxs-lookup"><span data-stu-id="10617-390">Use the `-flags` parameter.</span></span> <span data-ttu-id="10617-391">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-391">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="10617-392">**テストで使用する属性をコピーするためのサンプル スクリプトを提供できますか。**</span><span class="sxs-lookup"><span data-stu-id="10617-392">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="10617-393">サンプル – 現在、保証なし</span><span class="sxs-lookup"><span data-stu-id="10617-393">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="10617-394">このスクリプトは、ソース メールボックス (ソース値を取得する) と、ターゲットのオンプレミスの Active Directory ドメイン サービス (ADUser オブジェクトにスタンプを付け) の両方への接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="10617-394">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="10617-395">ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="10617-395">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="10617-396">これにより、宛先アカウントの削除のサイズが 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="10617-396">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="10617-397">**使用メールボックスを移動した後、1 日目に Outlook にアクセスする方法**</span><span class="sxs-lookup"><span data-stu-id="10617-397">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="10617-398">ドメインを所有できるのは 1 つのテナントだけのため、メールボックスの移動が完了すると、以前のプライマリ SMTPAddress はターゲット テナント内のユーザーに関連付けされません。新しいテナントに関連付けられているドメインのみ。</span><span class="sxs-lookup"><span data-stu-id="10617-398">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="10617-399">Outlook はユーザーの新しい UPN を使用してサービスに対する認証を行い、Outlook プロファイルはターゲット システム内のメールボックスと一致する従来のプライマリ SMTPAddress を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-399">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="10617-400">レガシ アドレスがターゲット システムに含ではなされていないので、Outlook プロファイルは新しく移動したメールボックスを検索するために接続されません。</span><span class="sxs-lookup"><span data-stu-id="10617-400">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="10617-401">この初期展開では、ユーザーは新しい UPN、プライマリ SMTP アドレスを使用してプロファイルを再構築し、OST コンテンツを再同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-401">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="10617-402">ユーザーのバッチ処理を完了に合わせて計画します。</span><span class="sxs-lookup"><span data-stu-id="10617-402">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="10617-403">Outlook クライアント プロファイルを作成し、それ以降の OST ファイルと OAB ファイルをクライアントにダウンロードする場合は、ネットワークの使用率と容量を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-403">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="10617-404">**テナント間の移行を設定または完了するには、どのような Exchange RBAC の役割のメンバーである必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="10617-404">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="10617-405">メールボックス移動を実行する際の委任された職務の前提に基づく役割のマトリックスがあります。</span><span class="sxs-lookup"><span data-stu-id="10617-405">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="10617-406">現在、2 つの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-406">Currently, two roles are required:</span></span>  

- <span data-ttu-id="10617-407">1 つ目の役割は、テナント/組織の境界内または組織の境界にコンテンツを移動する承認を確立する 1 回設定タスクです。</span><span class="sxs-lookup"><span data-stu-id="10617-407">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="10617-408">組織の制御からデータを移動する操作は、すべての企業にとって重要な懸念事項です。組織管理者 (OrgAdmin) の最高の役割を割り当てました。</span><span class="sxs-lookup"><span data-stu-id="10617-408">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="10617-409">この役割は、リモート組織での -MailboxMoveCapability を定義する新しい OrganizationRelationship を変更またはセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-409">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="10617-410">OrganizationRelationhip の他の属性はフェデレーション共有管理者が管理できるのに対し、OrgAdmin だけが MailboxMoveCapability 設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="10617-410">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="10617-411">実際の移動コマンドを実行する役割は、下位レベルの関数に委任できます。</span><span class="sxs-lookup"><span data-stu-id="10617-411">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="10617-412">メールボックスの移動の役割には、パラメーターを使用してメールボックスを組織内外に移動する機能が割り当 `-RemoteTenant` てられます。</span><span class="sxs-lookup"><span data-stu-id="10617-412">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="10617-413">**変換されたメールボックスの targetAddress (TargetDeliveryDomain) に対して選択されている SMTP アドレスをターゲットにする方法 (MailUser 変換へ)**</span><span class="sxs-lookup"><span data-stu-id="10617-413">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="10617-414">移動先オブジェクトの電子メール アドレス (proxyAddress) と一致して MailUser に変換する場合、MRS を使用して移動する Exchange メールボックスは、元のソース メールボックスで targetAddress を作成します。</span><span class="sxs-lookup"><span data-stu-id="10617-414">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="10617-415">このプロセスは、move コマンドに渡された -TargetDeliveryDomain 値を受け取り、ターゲット側のそのドメインに対応するプロキシを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-415">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="10617-416">一致が見つけると、一致する proxyAddress が使用され、変換されたメールボックス (現在は MailUser) オブジェクトに ExternalEmailAddress (targetAddress) が設定されます。</span><span class="sxs-lookup"><span data-stu-id="10617-416">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="10617-417">**メールボックスのアクセス許可の移行方法**</span><span class="sxs-lookup"><span data-stu-id="10617-417">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="10617-418">メールボックスのアクセス許可には、代理送信とメールボックス アクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10617-418">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="10617-419">代理人として送信 (AD:publicDelegates) は、ユーザーのメールボックスへのアクセス権を持つ受信者の DN を代理人として格納します。</span><span class="sxs-lookup"><span data-stu-id="10617-419">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="10617-420">この値は Active Directory に格納され、現在、メールボックスの移行の一部として移動されません。</span><span class="sxs-lookup"><span data-stu-id="10617-420">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="10617-421">移動元メールボックスに publicDelegates が設定されている場合は、実行してターゲット環境で MEU からメールボックスへの変換が完了したら、ターゲット メールボックスの publicDelegates を再サンプリングする必要があります `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 。</span><span class="sxs-lookup"><span data-stu-id="10617-421">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="10617-422">メールボックスに格納されているメールボックスのアクセス許可は、プリンシパルと代理人の両方がターゲット システムに移動すると、メールボックスと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="10617-422">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="10617-423">たとえば、ユーザーは、TestUser_7内のメールボックス に FullAccess TestUser_8付与SourceCompany.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="10617-423">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="10617-424">メールボックスの移動が完了TargetCompany.onmicrosoft.com、ターゲット ディレクトリに同じアクセス許可が設定されます。</span><span class="sxs-lookup"><span data-stu-id="10617-424">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="10617-425">ソース テナントとターゲット テナントの両方TestUser_7に *Get-MailboxPermission* を使用する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-425">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="10617-426">Exchange コマンドレットには、ソースとターゲットのプレフィックスが付いて表示されます。</span><span class="sxs-lookup"><span data-stu-id="10617-426">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="10617-427">移動前のメールボックスアクセス許可の出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-427">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="10617-428">移動後のメールボックスアクセス許可の出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-428">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="10617-429">テナント間のメールボックスと予定表のアクセス許可はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10617-429">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="10617-430">プリンシパルと代理人を統合移動バッチに整理して、接続されたメールボックスが移行元テナントから同時に移行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-430">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="10617-431">**移行を有効にするには、どの X500 プロキシをターゲットの MailUser プロキシ アドレスに追加する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="10617-431">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="10617-432">テナント間メールボックスの移行では、移動元メールボックス オブジェクトの LegacyExchangeDN 値が、移動先の MailUser オブジェクトの x500 電子メール アドレスとしてスタンプされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-432">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="10617-433">例:</span><span class="sxs-lookup"><span data-stu-id="10617-433">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="10617-434">この X500 プロキシに加えて、ソース内のメールボックスからターゲット内のメールボックスに、すべての X500 プロキシをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-434">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="10617-435">**Azure Key Vault は必要ですか。また、いつトランザクションが行われたか。**</span><span class="sxs-lookup"><span data-stu-id="10617-435">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="10617-436">はい、移行を承認する証明書を保存するために Key Vault を使用するには、Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="10617-436">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="10617-437">ユーザー名 & パスワードを使用して移行元への認証を行うオンボード移行とは異なり、テナント間メールボックスの移行では OAuth とこの証明書をシークレット/資格情報として使用します。</span><span class="sxs-lookup"><span data-stu-id="10617-437">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="10617-438">Key Vault へのアクセスは、移行の開始時と終了時に 1 回、増分同期時に 24 時間ごとに 1 回アクセスされるのと同様に、すべてのメールボックスの移行を通じて維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-438">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="10617-439">ARK のコストの詳細については、こちらを参照 [してください]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="10617-439">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="10617-440">**バッチ処理に関する推奨事項はありますか?**</span><span class="sxs-lookup"><span data-stu-id="10617-440">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="10617-441">バッチあたり 2,000 のメールボックスを超えないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="10617-441">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="10617-442">同期中にエンド ユーザーに影響が出ない場合は、カットオーバー日の 2 週間前にバッチを送信することを強く推奨します。50,000 を超えるメールボックスの数量に関するガイダンスが必要な場合は、次のページでエンジニアリング フィードバック配布リストcrosstenantmigrationpreview@service.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="10617-442">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="10617-443">**顧客キーでサービスの暗号化を使用する場合**</span><span class="sxs-lookup"><span data-stu-id="10617-443">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="10617-444">メールボックスは移動前に復号化されます。</span><span class="sxs-lookup"><span data-stu-id="10617-444">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="10617-445">引き続き必要な場合は、ターゲット テナントで顧客キーが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-445">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="10617-446">詳細 [については、](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10617-446">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="10617-447">**推定移行時間は何時ですか?**</span><span class="sxs-lookup"><span data-stu-id="10617-447">**What is the estimated migration time?**</span></span>

<span data-ttu-id="10617-448">移行を計画する際に役立つ、次[](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)の表に、一括メールボックスの移行または個々の移行が完了すると予想される場合のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="10617-448">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="10617-449">これらの見積もりは、以前の顧客移行のデータ分析に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="10617-449">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="10617-450">どの環境も一意なので、移行の正確な速度は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="10617-450">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="10617-451">この機能は現在プレビュー段階であり、SLA および該当するサービス レベルは、この機能のプレビュー状態中のパフォーマンスまたは可用性の問題には適用されません。</span><span class="sxs-lookup"><span data-stu-id="10617-451">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="10617-452">既知の問題</span><span class="sxs-lookup"><span data-stu-id="10617-452">Known issues</span></span>  

-  <span data-ttu-id="10617-453">**問題: 自動拡張アーカイブを移行できません。**</span><span class="sxs-lookup"><span data-stu-id="10617-453">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="10617-454">テナント間の移行機能は、特定のユーザーのプライマリ メールボックスとアーカイブ メールボックスの移行をサポートします。</span><span class="sxs-lookup"><span data-stu-id="10617-454">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="10617-455">ただし、ソース内のユーザーが自動拡張アーカイブ (複数のアーカイブ メールボックスを意味する) を持つ場合、この機能は追加のアーカイブを移行できません。</span><span class="sxs-lookup"><span data-stu-id="10617-455">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="10617-456">**問題: 所有されていない smtp proxyAddress ブロック MRS を持つ Cloud MailUsers がバックグラウンドで移動します。**</span><span class="sxs-lookup"><span data-stu-id="10617-456">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="10617-457">ターゲット テナントの MailUser オブジェクトを作成する場合は、すべての SMTP プロキシ アドレスがターゲット テナント組織に属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-457">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="10617-458">ローカル テナントに属さないターゲット メール ユーザーに SMTP proxyAddress が存在する場合、MailUser から Mailbox への変換は防止されます。</span><span class="sxs-lookup"><span data-stu-id="10617-458">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="10617-459">これは、メールボックス オブジェクトが、テナントが権限を持つドメイン (テナントによって要求されたドメイン) からのみメールを送信できるという保証のためです。</span><span class="sxs-lookup"><span data-stu-id="10617-459">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="10617-460">Azure AD Connect を使用してオンプレミスからユーザーを同期する場合、メールボックスが存在するソース テナント (laran@contoso.onmicrosoft.com) を指す ExternalEmailAddress を使用してオンプレミスの MailUser オブジェクトをプロビジョニングし、PrimarySMTPAddress をターゲット テナント (Lara.Newton@northwind.com) に存在するドメインとしてスタンプします。</span><span class="sxs-lookup"><span data-stu-id="10617-460">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="10617-461">これらの値はテナントに同期され、適切なメール ユーザーがプロビジョニングされ、移行の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="10617-461">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="10617-462">オブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-462">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="10617-463">電子 *contoso.onmicrosoft.com\*\*アドレスが* EmailAddresses / proxyAddresses 配列に存在しない。</span><span class="sxs-lookup"><span data-stu-id="10617-463">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="10617-464">**問題: "外部" プライマリ SMTP アドレスを持つ MailUser オブジェクトが、"内部" の会社が要求したドメインに変更またはリセットされる**</span><span class="sxs-lookup"><span data-stu-id="10617-464">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="10617-465">MailUser オブジェクトは、ローカル以外のメールボックスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="10617-465">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="10617-466">テナント間のメールボックス移行の場合は、MailUser オブジェクトを使用して、移動元メールボックス (ターゲット組織の観点から) またはターゲット メールボックス (移行元組織の観点から) を表します。</span><span class="sxs-lookup"><span data-stu-id="10617-466">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="10617-467">MailUsers には、ディレクトリ内のメールボックス ユーザーの表示される SMTP アドレスを表す、実際のメールボックス (ProxyTest@fabrikam.onmicrosoft.com) の smtp アドレスと primarySMTP アドレスをポイントする ExternalEmailAddress (targetAddress) があります。</span><span class="sxs-lookup"><span data-stu-id="10617-467">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="10617-468">一部の組織では、プライマリ SMTP アドレスを外部 SMTP アドレスとして表示し、ローカル テナントによって所有/検証されるアドレス (fabrikam.com など、 contoso.com など) として表示しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="10617-468">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="10617-469">ただし、ライセンス操作によって Exchange サービス プラン オブジェクトが MailUser に適用されると、プライマリ SMTP アドレスが変更され、ローカル組織 (contoso.com) によって確認されたドメインとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="10617-469">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="10617-470">次の 2 つの潜在的な理由があります。</span><span class="sxs-lookup"><span data-stu-id="10617-470">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="10617-471">Exchange サービス プランが MailUser に適用されると、Azure AD プロセスはプロキシ スクラブの適用を開始し、ローカル組織が別のテナントからメールを送信、スプーフィング、またはメールを送信できないか確認します。</span><span class="sxs-lookup"><span data-stu-id="10617-471">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="10617-472">これらのサービス プランを持つ受信者オブジェクトの SMTP アドレスは、そのアドレスがローカル組織によって確認されていない場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="10617-472">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="10617-473">例の場合と同様に、Fabikam.com ドメインは contoso.onmicrosoft.com テナントによって検証されないので、スクラブによってそのドメインfabrikam.comされます。</span><span class="sxs-lookup"><span data-stu-id="10617-473">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="10617-474">移行前または移行後にこれらの外部ドメインを MailUser に保持する場合は、移行が完了した後、または移行前にライセンスを削除して、ユーザーに予期される外部ブランド化が適用されるかどうかを確認するために、移行プロセスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-474">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="10617-475">メール サービスに影響を与えずに、メールボックス オブジェクトに適切なライセンスが与えされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10617-475">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="10617-476">テナント内の MailUser のサービス プランを削除するスクリプトContoso.onmicrosoft.com次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-476">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="10617-477">割り当てられた ServicePlans のセットの結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10617-477">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="10617-478">ユーザーの PrimarySMTPAddress がスクラブされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="10617-478">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="10617-479">ドメインfabrikam.comは、contoso.onmicrosoft.com テナントによって所有されていないので、ディレクトリに表示されるプライマリ SMTP アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="10617-479">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="10617-480">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="10617-480">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="10617-481">msExchRemoteRecipientType が 8 (DeprovisionMailbox) に設定されている場合、ターゲット テナントに移行されるオンプレミスの MailUser の場合、Azure のプロキシ スクラブ ロジックは、所有されていないドメインを削除し、primarySMTP を所有ドメインにリセットします。</span><span class="sxs-lookup"><span data-stu-id="10617-481">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="10617-482">オンプレミスの MailUser で msExchRemoteRecipientType をクリアすると、プロキシ スクラブ ロジックは適用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="10617-482">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="10617-483">以下に、Exchange Online を含む、可能なサービス プランの完全なセットを示します。</span><span class="sxs-lookup"><span data-stu-id="10617-483">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="10617-484">Name</span><span class="sxs-lookup"><span data-stu-id="10617-484">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="10617-485">Advanced eDiscovery Storage (500GB)</span><span class="sxs-lookup"><span data-stu-id="10617-485">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="10617-486">顧客ロックボックス</span><span class="sxs-lookup"><span data-stu-id="10617-486">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="10617-487">データ損失防止</span><span class="sxs-lookup"><span data-stu-id="10617-487">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="10617-488">Exchange Enterprise CAL サービス (EOP、DLP)</span><span class="sxs-lookup"><span data-stu-id="10617-488">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="10617-489">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="10617-489">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="10617-490">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="10617-490">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="10617-491">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="10617-491">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="10617-492">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="10617-492">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="10617-493">Exchange Online (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="10617-493">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="10617-494">Exchange Online 用の Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="10617-494">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="10617-495">Exchange Server 用の Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="10617-495">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="10617-496">Exchange Online 非アクティブユーザー アドオン</span><span class="sxs-lookup"><span data-stu-id="10617-496">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="10617-497">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="10617-497">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="10617-498">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="10617-498">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="10617-499">Exchange Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="10617-499">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="10617-500">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="10617-500">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="10617-501">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="10617-501">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="10617-502">情報バリア</span><span class="sxs-lookup"><span data-stu-id="10617-502">Information Barriers</span></span>                              |
   | <span data-ttu-id="10617-503">Information Protection for Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="10617-503">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="10617-504">Information Protection for Office 365 - Standard</span><span class="sxs-lookup"><span data-stu-id="10617-504">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="10617-505">MyAnalytics による分析情報</span><span class="sxs-lookup"><span data-stu-id="10617-505">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="10617-506">Microsoft 365 Advanced Auditing</span><span class="sxs-lookup"><span data-stu-id="10617-506">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="10617-507">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="10617-507">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="10617-508">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="10617-508">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="10617-509">Microsoft MyAnalytics (フル機能)</span><span class="sxs-lookup"><span data-stu-id="10617-509">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="10617-510">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="10617-510">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="10617-511">Microsoft Defender for Office 365 (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="10617-511">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="10617-512">Microsoft Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="10617-512">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="10617-513">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="10617-513">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="10617-514">Office 365 でのプレミアム暗号化</span><span class="sxs-lookup"><span data-stu-id="10617-514">Premium Encryption in Office 365</span></span>                  |
    
