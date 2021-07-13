---
title: テナント間でのメールボックスの移行
description: メールボックスをテナント間またはMicrosoft 365間Office 365する方法。
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
ms.openlocfilehash: 471682b6f830609ef4ff9241bdaa515c97ca2d8d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394907"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="ed54c-103">テナント間メールボックスの移行 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ed54c-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="ed54c-104">以前は、Exchange Online テナントが同じ Exchange Online サービス内の別のテナントにメールボックスを移動する必要がある場合、メールボックスをオンプレミスに完全にオフボードしてから、新しいテナントにオンボードする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="ed54c-105">新しいクロステナント メールボックス移行機能により、移行元テナントとターゲット テナントの両方のテナント管理者は、オンプレミス システムでのインフラストラクチャの依存関係を最小限に抑えたテナント間でメールボックスを移動できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="ed54c-106">これにより、オフボードメールボックスとオンボードメールボックスが不要になります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="ed54c-107">一般的に、合併や売却の際には、ユーザーとコンテンツを新しいテナントに移動する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="ed54c-108">ターゲット テナント管理者が移動を実行すると、オンプレミスからクラウド オンボーディング移行に似たプル移動と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="ed54c-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="ed54c-109">クロステナント Exchange メールボックスの移動は、テナント管理者によって完全にセルフサービスされ、ユーザーを新しい組織に移行するために必要な大規模なワークフローにスクリプト化できる既知のインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="ed54c-110">管理者は、メールボックスの移動管理役割で使用できるコマンドレットを使用して、テナント `New-MigrationBatch` 間の移動を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="ed54c-111">移動プロセスには、メールボックスの同期と完了時のテナント承認チェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span>

<span data-ttu-id="ed54c-112">移行するユーザーは、移行先のテナント Exchange Online MailUsers として存在し、テナント間の移動を有効にするには、特定の属性でマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="ed54c-113">ターゲット テナントで適切に設定されていないユーザーの移動はシステムによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>

<span data-ttu-id="ed54c-114">移動が完了すると、ソース システム メールボックスは MailUser に変換され、targetAddress (Exchange の ExternalEmailAddress として表示されます) は、宛先テナントへのルーティング アドレスでスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="ed54c-115">このプロセスは、従来の MailUser をソース テナントに残し、一時期の共同存在とメール ルーティングを可能にします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="ed54c-116">ビジネス プロセスで許可されている場合、ソース テナントはソース MailUser を削除するか、メール連絡先に変換できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span>

<span data-ttu-id="ed54c-117">ハイブリッドまたはクラウドExchange、または 2 つの任意の組み合わせのテナントに対して、複数テナント間のメールボックス移行がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="ed54c-118">この記事では、テナント間メールボックスの移動のプロセスについて説明し、コンテンツ移動のソース テナントとターゲット テナントを準備する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="ed54c-119">ソーステナントとターゲット テナントの準備</span><span class="sxs-lookup"><span data-stu-id="ed54c-119">Preparing source and target tenants</span></span>

<span data-ttu-id="ed54c-120">クロステナント 移行機能Exchange移行には、クロステナント移行の承認とスコープが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="ed54c-121">Azure Enterprise アプリケーションと Key Vault ストレージ ソリューションを使用して、テナント管理者は、1 つのテナントから別のテナントへの Exchange Online メールボックス移行の承認とスコープの両方を管理する権限を与えました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="ed54c-122">テナント間メールボックスの移動は、テナントペア間の認証に使用される Azure Active Directory (Azure AD) アプリケーションを確立するための招待と同意モデルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="ed54c-123">組織の関係や移行エンドポイントなどの追加コンポーネントも必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="ed54c-124">このセクションには、ターゲット ディレクトリ内の MailUser ユーザー オブジェクトを準備するために必要な具体的な手順は含まれています。また、移行バッチを送信するためのサンプル コマンドも含めありません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="ed54c-125">この情報については [、「移行対象のユーザー オブジェクトを準備する」](#prepare-target-user-objects-for-migration) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed54c-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed54c-126">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed54c-126">Prerequisites</span></span>

<span data-ttu-id="ed54c-127">テナント間メールボックス移動機能では [、Azure Key Vault](/azure/key-vault/basic-concepts) がテナントペア固有の Azure アプリケーションを確立して、あるテナントから別のテナントへのメールボックス移行を認証および承認するために使用される証明書/シークレットを安全に保存してアクセスする必要があります。テナント間で証明書/シークレットを共有するための要件は削除されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span>

<span data-ttu-id="ed54c-128">開始する前に、Azure Key Vault、Move Mailbox Application、EXO Migration Endpoint、EXO Organization Relationship を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="ed54c-129">通常、グローバル管理者には、すべての構成手順を実行するアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="ed54c-130">さらに、セットアップを実行する前に、ソース テナント内のメールが有効なセキュリティ グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="ed54c-131">これらのグループは、ソース (またはリソースとも呼ばれる) テナントからターゲット テナントに移動できるメールボックスの一覧の範囲を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="ed54c-132">これにより、移行元テナント管理者は、移動する必要があるメールボックスの特定のセットを制限または範囲指定し、意図しないユーザーが移行されるのを防ぐことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="ed54c-133">入れ子になったグループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-133">Nested groups are not supported.</span></span>

<span data-ttu-id="ed54c-134">また、信頼できるパートナー企業 (メールボックスを移動する相手) と通信して、テナント ID を取得Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="ed54c-135">このテナント ID は、[組織の関係] フィールドで使用 `DomainName` されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="ed54c-136">サブスクリプションのテナント ID を取得するには、サブスクリプションにサインインMicrosoft 365 管理センターに移動します [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) 。</span><span class="sxs-lookup"><span data-stu-id="ed54c-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="ed54c-137">Tenant ID プロパティのコピー アイコンをクリックしてクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="ed54c-138">プロセスの動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="メールボックスの移行のためのテナントの準備。":::

<span data-ttu-id="ed54c-140">[このイメージのより大きなバージョンを参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
-->

### <a name="prepare-tenants"></a><span data-ttu-id="ed54c-141">テナントの準備</span><span class="sxs-lookup"><span data-stu-id="ed54c-141">Prepare tenants</span></span>

<span data-ttu-id="ed54c-142">高レベルでは、セットアップ スクリプトの実行時に次の構成アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="ed54c-143">ターゲット テナントを準備します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="ed54c-144">既存の Azure リソース グループが指定されていない場合は、新しい Azure リソース グループが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="ed54c-145">既存の Key Vault が指定されていない場合は、新しいキー コンテナーが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="ed54c-146">メールボックス移行アプリケーション (SCRIPT) のOffice 365 Exchange Onlineアクセス ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="ed54c-147">移行アプリケーション (SCRIPT) にシークレットを保持するために、新しい証明書 (または指定されている場合は既存の証明書) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="ed54c-148">新しい Azure ADアプリケーションが作成されます (SCRIPT)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="ed54c-149">証明書/シークレットが移行アプリケーション (SCRIPT) にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="ed54c-150">メールボックス移行のアクセス許可は、アプリケーション (SCRIPT) に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="ed54c-151">展開スクリプトは、ターゲット管理者が自分のアプリケーション (SCRIPT) に同意するまで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="ed54c-152">ターゲット テナント管理者は、アプリケーションに与えられたアクセス許可 (MANUAL) に同意します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="ed54c-153">組織の関係は、ターゲット テナント (SCRIPT) に対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="ed54c-154">移行エンドポイントが作成され、メールボックスをターゲット テナント (SCRIPT) にプルします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="ed54c-155">ソース テナントを準備します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="ed54c-156">移行元テナント管理者は、ターゲット テナント (MANUAL) からのメールボックス移行アプリケーションの招待に対する同意を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="ed54c-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="ed54c-157">移行元テナント管理者は、移行アプリケーション (MANUAL) によって移動できるメールボックスの一覧を含むメールが有効なセキュリティ グループをテナントに作成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="ed54c-158">OAuth 検証で移動要求 (SCRIPT) を受け入れるには、メールボックス移行アプリケーションを使用する必要があるという組織の関係がターゲット テナントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="ed54c-159">ターゲット テナント管理者の手順</span><span class="sxs-lookup"><span data-stu-id="ed54c-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="ed54c-160">ターゲット テナントのSetupCrossTenantRelationshipForTargetTenant.ps1のスクリプトを、新しいリポジトリから[GitHubします](https://github.com/microsoft/cross-tenant/releases/tag/Preview)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span>
2. <span data-ttu-id="ed54c-161">スクリプト (SetupCrossTenantRelationshipForTargetTenant.ps1) を、スクリプトを実行するコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="ed54c-162">ターゲット テナントへのリモート PowerShell 接続Exchange Online作成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="ed54c-163">繰り返しますが、Azure Key Vault ストレージと証明書、Move Mailbox アプリケーション、EXO Migration Endpoint、EXO Organization Relationship を構成するために、展開スクリプトを実行するために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="ed54c-164">ファイル フォルダー ディレクトリをスクリプトの場所に変更するか、スクリプトが現在リモート PowerShell セッションの現在の場所に保存されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="ed54c-165">次のパラメーターと値を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-165">Run the script with the following parameters and values.</span></span>

   |<span data-ttu-id="ed54c-166">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed54c-166">Parameter</span></span>|<span data-ttu-id="ed54c-167">値</span><span class="sxs-lookup"><span data-stu-id="ed54c-167">Value</span></span>|<span data-ttu-id="ed54c-168">必須またはオプション</span><span class="sxs-lookup"><span data-stu-id="ed54c-168">Required or Optional</span></span>
   |---|---|---|
   |<span data-ttu-id="ed54c-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="ed54c-169">-TargetTenantDomain</span></span>|<span data-ttu-id="ed54c-170">fabrikam ドメインなどのターゲット \. テナント ドメイン onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span>|<span data-ttu-id="ed54c-171">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-171">Required</span></span>|
   |<span data-ttu-id="ed54c-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="ed54c-172">-ResourceTenantDomain</span></span>|<span data-ttu-id="ed54c-173">contoso ドメインなどのソース \. テナント ドメイン onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span>|<span data-ttu-id="ed54c-174">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-174">Required</span></span>|
   |<span data-ttu-id="ed54c-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="ed54c-175">-ResourceTenantAdminEmail</span></span>|<span data-ttu-id="ed54c-176">ソース テナント管理者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="ed54c-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="ed54c-177">これは、ターゲット管理者から送信されたメールボックス移行アプリケーションの使用に同意する移行元テナント管理者です。これは、アプリケーションのメール招待を受け取る管理者です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span>|<span data-ttu-id="ed54c-178">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-178">Required</span></span>|
   |<span data-ttu-id="ed54c-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="ed54c-179">-ResourceTenantId</span></span>|<span data-ttu-id="ed54c-180">ソース テナント組織 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-180">Source tenant organization ID (GUID).</span></span>|<span data-ttu-id="ed54c-181">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-181">Required</span></span>|
   |<span data-ttu-id="ed54c-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="ed54c-182">-SubscriptionId</span></span>|<span data-ttu-id="ed54c-183">リソースの作成に使用する Azure サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="ed54c-183">The Azure subscription to use for creating resources.</span></span>|<span data-ttu-id="ed54c-184">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-184">Required</span></span>|
   |<span data-ttu-id="ed54c-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="ed54c-185">-ResourceGroup</span></span>|<span data-ttu-id="ed54c-186">キー コンテナーを含む、または含まれる Azure リソース グループ名。</span><span class="sxs-lookup"><span data-stu-id="ed54c-186">Azure resource group name that contains or will contain the Key Vault.</span></span>|<span data-ttu-id="ed54c-187">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-187">Required</span></span>|
   |<span data-ttu-id="ed54c-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="ed54c-188">-KeyVaultName</span></span>|<span data-ttu-id="ed54c-189">メールボックス移行アプリケーション証明書/シークレットを格納する Azure Key Vault インスタンス。</span><span class="sxs-lookup"><span data-stu-id="ed54c-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span>|<span data-ttu-id="ed54c-190">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-190">Required</span></span>|
   |<span data-ttu-id="ed54c-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="ed54c-191">-CertificateName</span></span>|<span data-ttu-id="ed54c-192">キー コンテナーで証明書を生成または検索する場合の証明書名。</span><span class="sxs-lookup"><span data-stu-id="ed54c-192">Certificate name when generating or searching for certificate in key vault.</span></span>|<span data-ttu-id="ed54c-193">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-193">Required</span></span>|
   |<span data-ttu-id="ed54c-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="ed54c-194">-CertificateSubject</span></span>|<span data-ttu-id="ed54c-195">AZURE Key Vault 証明書のサブジェクト名 (CN=contoso_fabrikam など)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span>|<span data-ttu-id="ed54c-196">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-196">Required</span></span>|
   |<span data-ttu-id="ed54c-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="ed54c-197">-AzureResourceLocation</span></span>|<span data-ttu-id="ed54c-198">Azure リソース グループとキー コンテナーの場所。</span><span class="sxs-lookup"><span data-stu-id="ed54c-198">The location of the Azure resource group and key vault.</span></span>|<span data-ttu-id="ed54c-199">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-199">Required</span></span>|
   |<span data-ttu-id="ed54c-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="ed54c-200">-ExistingApplicationId</span></span>|<span data-ttu-id="ed54c-201">既に作成されている場合に使用するメール移行アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="ed54c-201">Mail migration application to use if one was already created.</span></span>|<span data-ttu-id="ed54c-202">省略可能</span><span class="sxs-lookup"><span data-stu-id="ed54c-202">Optional</span></span>|
   |<span data-ttu-id="ed54c-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="ed54c-203">-AzureAppPermissions</span></span>|<span data-ttu-id="ed54c-204">メールボックス移行アプリケーションに与える必要があるアクセス許可 (Exchange または MSGraph (メールボックスを移動するための Exchange、このアプリケーションを使用してリソース テナントに同意リンクの招待を送信するための MSGraph)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span>|<span data-ttu-id="ed54c-205">必須</span><span class="sxs-lookup"><span data-stu-id="ed54c-205">Required</span></span>|
   |<span data-ttu-id="ed54c-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="ed54c-206">-UseAppAndCertGeneratedForSendingInvitation</span></span>|<span data-ttu-id="ed54c-207">移行先テナント管理者に同意リンクの招待を送信するために使用する移行用に作成されたアプリケーションを使用するパラメーター。存在しない場合は、ターゲット管理者の資格情報が Azure 招待マネージャーに接続し、招待をターゲット管理者として送信するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span>|<span data-ttu-id="ed54c-208">省略可能</span><span class="sxs-lookup"><span data-stu-id="ed54c-208">Optional</span></span>|
   |<span data-ttu-id="ed54c-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="ed54c-209">-KeyVaultAuditStorageAccountName</span></span>|<span data-ttu-id="ed54c-210">Key Vault の監査ログが格納されるストレージ アカウント。</span><span class="sxs-lookup"><span data-stu-id="ed54c-210">The storage account where Key Vault’s audit logs would be stored.</span></span>|<span data-ttu-id="ed54c-211">省略可能</span><span class="sxs-lookup"><span data-stu-id="ed54c-211">Optional</span></span>|
   |<span data-ttu-id="ed54c-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="ed54c-212">-KeyVaultAuditStorageResourceGroup</span></span>|<span data-ttu-id="ed54c-213">Key Vault 監査ログを格納するためのストレージ アカウントを含むリソース グループ。</span><span class="sxs-lookup"><span data-stu-id="ed54c-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span>|<span data-ttu-id="ed54c-214">省略可能</span><span class="sxs-lookup"><span data-stu-id="ed54c-214">Optional</span></span>|
   ||||

    > [!NOTE]
    > <span data-ttu-id="ed54c-215">スクリプトを実行する前に、Azure AD PowerShell モジュールがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ed54c-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="ed54c-216">インストール手順については [、こちらを](/powershell/azure/install-az-ps) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed54c-216">Please refer to [here](/powershell/azure/install-az-ps) for installation steps</span></span>

6. <span data-ttu-id="ed54c-217">スクリプトは一時停止し、このプロセス中に作成されたExchange移行アプリケーションに同意するか、同意を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="ed54c-218">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-218">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> # Note: the below User.Invite.All permission is optional, and will only be used to retrieve access token to send invitation email to source tenant
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - User.Invite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```

7. <span data-ttu-id="ed54c-219">リモート PowerShell セッションに URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="ed54c-220">テナントの同意のために提供されたリンクをコピーし、Web ブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="ed54c-221">グローバル管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="ed54c-222">次の画面が表示された場合は、[同意する] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed54c-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="[アクセス許可を受け入れる] ダイアログ ボックス":::

9. <span data-ttu-id="ed54c-224">リモート PowerShell セッションに戻り、Enter キーを押して続行します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="ed54c-225">スクリプトは、残りのセットアップ オブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="ed54c-226">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="ed54c-227">ターゲット管理者のセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="ed54c-228">ソース テナント管理者の手順</span><span class="sxs-lookup"><span data-stu-id="ed54c-228">Step-by-step instructions for the source tenant admin</span></span>

1. <span data-ttu-id="ed54c-229">セットアップ中にターゲット管理者によって指定された -ResourceTenantAdminEmail としてメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="ed54c-230">ターゲット テナントから電子メールの招待状を見つけて、[メールの送信] ボタン **はじめに** します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="[招待された] ダイアログ ボックス":::

2. <span data-ttu-id="ed54c-232">[承諾 **] を選択** して招待を承諾します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="アクセス許可を受け入れるダイアログ ボックス":::

   > [!NOTE]
   > <span data-ttu-id="ed54c-234">このメールを受け取らなか、見つからない場合は、ターゲット テナント管理者に直接 URL が提供されたので、招待を受け入れできます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="ed54c-235">URL は、ターゲット テナント管理者のリモート PowerShell セッションのトランスクリプト内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="ed54c-236">Microsoft 365 管理センター セッションまたはリモート PowerShell セッションで、1 つ以上のメールが有効なセキュリティ グループを作成して、ターゲット テナントがソース テナントからターゲット テナントにプル (移動) できるメールボックスの一覧を制御します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="ed54c-237">このグループを事前に設定する必要はありますが、セットアップ 手順 (スクリプト) を実行するには、少なくとも 1 つのグループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="ed54c-238">ネスト グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-238">Nest groups are not supported.</span></span>

4. <span data-ttu-id="ed54c-239">ソース テナントのSetupCrossTenantRelationshipForResourceTenant.ps1のスクリプトを、次のリポジトリからGitHubダウンロードします [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 。</span><span class="sxs-lookup"><span data-stu-id="ed54c-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span>

5. <span data-ttu-id="ed54c-240">管理者のアクセス許可を使用して、ソース テナントへのリモート PowerShell 接続Exchange作成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="ed54c-241">グローバル管理者のアクセス許可は、ソース テナントを構成するために必要ではなく、Azure アプリケーションの作成プロセスのためにターゲット テナントのみを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="ed54c-242">ディレクトリをスクリプトの場所に変更するか、スクリプトが現在リモート PowerShell セッションの現在の場所に保存されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="ed54c-243">次の必須パラメーターと値を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-243">Run the script with the following required parameters and values.</span></span>

   |<span data-ttu-id="ed54c-244">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ed54c-244">Parameter</span></span>|<span data-ttu-id="ed54c-245">値</span><span class="sxs-lookup"><span data-stu-id="ed54c-245">Value</span></span>|
   |---|---|
   |<span data-ttu-id="ed54c-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="ed54c-246">-SourceMailboxMovePublishedScopes</span></span>|<span data-ttu-id="ed54c-247">移行の対象である ID/メールボックスのソース テナントによって作成されたメールが有効なセキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="ed54c-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span>|
   |<span data-ttu-id="ed54c-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="ed54c-248">-ResourceTenantDomain</span></span>|<span data-ttu-id="ed54c-249">contoso ドメインなどのソース テナント \. ドメイン onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span>|
   |<span data-ttu-id="ed54c-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="ed54c-250">-ApplicationId</span></span>|<span data-ttu-id="ed54c-251">移行に使用されるアプリケーションの Azure アプリケーション ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="ed54c-252">Azure portal (Azure AD、Enterprise アプリケーション、アプリ名、アプリケーション ID) を使用するか、招待メールに含まれるアプリケーション ID。</span><span class="sxs-lookup"><span data-stu-id="ed54c-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>|
   |<span data-ttu-id="ed54c-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="ed54c-253">-TargetTenantDomain</span></span>|<span data-ttu-id="ed54c-254">fabrikam ドメインなどのターゲット テナント \. ドメイン onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span>|
   |<span data-ttu-id="ed54c-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="ed54c-255">-TargetTenantId</span></span>|<span data-ttu-id="ed54c-256">ターゲット テナントのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="ed54c-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="ed54c-257">たとえば、azure は contoso ADテナントのテナント ID \. onmicrosoft.com します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span>|
   |||

    <span data-ttu-id="ed54c-258">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-258">Here is an example.</span></span>

    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.
    ```

<span data-ttu-id="ed54c-259">ソース管理のセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="ed54c-260">セットアップを確認する</span><span class="sxs-lookup"><span data-stu-id="ed54c-260">Verify setup</span></span>

<span data-ttu-id="ed54c-261">移行元テナントとターゲット テナントの両方の組織関係と、ターゲット内の移行エンドポイントが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="ed54c-262">ターゲット テナント</span><span class="sxs-lookup"><span data-stu-id="ed54c-262">Target tenant</span></span>

##### <a name="organization-relationship"></a><span data-ttu-id="ed54c-263">組織の関係</span><span class="sxs-lookup"><span data-stu-id="ed54c-263">Organization relationship</span></span>

<span data-ttu-id="ed54c-264">組織リレーションシップ オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="ed54c-265">次に例を示します：</span><span class="sxs-lookup"><span data-stu-id="ed54c-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound
```

##### <a name="migration-endpoint"></a><span data-ttu-id="ed54c-266">移行エンドポイント</span><span class="sxs-lookup"><span data-stu-id="ed54c-266">Migration endpoint</span></span>

<span data-ttu-id="ed54c-267">移行エンドポイント オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="ed54c-268">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308
```

#### <a name="source-tenant"></a><span data-ttu-id="ed54c-269">ソース テナント</span><span class="sxs-lookup"><span data-stu-id="ed54c-269">Source tenant</span></span>

##### <a name="organization-relationship"></a><span data-ttu-id="ed54c-270">組織の関係</span><span class="sxs-lookup"><span data-stu-id="ed54c-270">Organization relationship</span></span>

<span data-ttu-id="ed54c-271">組織リレーションシップ オブジェクトが作成され、このコマンドで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="ed54c-272">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="ed54c-273">セットアップ スクリプトの確認</span><span class="sxs-lookup"><span data-stu-id="ed54c-273">Verify Setup Script</span></span>

<span data-ttu-id="ed54c-274">ソーステナントまたはターゲット テナントの構成中にエラーが発生した場合は、VerifySetup.ps1 スクリプトをGitHubし[、](https://github.com/microsoft/cross-tenant/releases/tag/Preview)出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="ed54c-275">次に、ターゲット テナントでVerifySetup.ps1例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="ed54c-276">次に、ソース テナントのVerifySetup.ps1例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="ed54c-277">メールボックスを元のソースに戻す</span><span class="sxs-lookup"><span data-stu-id="ed54c-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="ed54c-278">メールボックスを元のソース テナントに戻す必要がある場合は、新しいソース テナントと新しいターゲット テナントの両方で同じ手順とスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="ed54c-279">既存の Organization Relationship オブジェクトは更新または追加され、再作成されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="ed54c-280">移行用にターゲット ユーザー オブジェクトを準備する</span><span class="sxs-lookup"><span data-stu-id="ed54c-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="ed54c-281">移行するユーザーは、テナント間の移動を有効にするには、ターゲット テナントと Exchange Online システム (MailUsers) に特定の属性がマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="ed54c-282">ターゲット テナントで適切に設定されていないユーザーの移動はシステムによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="ed54c-283">次のセクションでは、ターゲット テナントの MailUser オブジェクト要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ed54c-284">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed54c-284">Prerequisites</span></span>

<span data-ttu-id="ed54c-285">次のオブジェクトと属性がターゲット組織で設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-285">You must ensure the following objects and attributes are set in the target organization.</span></span>

1. <span data-ttu-id="ed54c-286">移行元組織から移動するメールボックスの場合は、ターゲット組織で MailUser オブジェクトを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span>

   - <span data-ttu-id="ed54c-287">ターゲット MailUser には、ソース メールボックスからの属性、または新しい User オブジェクトが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="ed54c-288">ExchangeGUID (ソースからターゲットへの直接フロー) – メールボックス GUID が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="ed54c-289">移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-289">The move process will not proceed if this is not present on target object.</span></span>
      - <span data-ttu-id="ed54c-290">ArchiveGUID (ソースからターゲットへの直接フロー) – アーカイブ GUID が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="ed54c-291">移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="ed54c-292">(これは、ソース メールボックスがアーカイブが有効になっている場合にのみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-292">(This is only required if the source mailbox is Archive enabled).</span></span>
      - <span data-ttu-id="ed54c-293">LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – LegacyExchangeDN は、ターゲット MailUser に x500: proxyAddress として存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="ed54c-294">さらに、ソース メールボックスからターゲット メール ユーザーにすべての x500 アドレスをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-294">In addition, you also need to copy all x500 addresses from the source mailbox to the target mail user.</span></span> <span data-ttu-id="ed54c-295">移動プロセスは、ターゲット オブジェクトに存在しない場合は続行できません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-295">The move processes will not proceed if these are not present on the target object.</span></span> 
      - <span data-ttu-id="ed54c-296">UserPrincipalName – UPN は、ユーザーの新しい ID またはターゲット企業 (たとえば、user@northwindtraders.onmicrosoft.com) に合 user@northwindtraders.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-296">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span>
      - <span data-ttu-id="ed54c-297">プライマリ SMTPAddress – プライマリ SMTP アドレスは、ユーザーの新しい会社 (たとえば、user@northwind.com) に合 user@northwind.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-297">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span>
      - <span data-ttu-id="ed54c-298">TargetAddress/ExternalEmailAddress – MailUser は、ソース テナントでホストされているユーザーの現在のメールボックスを参照します (たとえば、user@contoso.onmicrosoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-298">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="ed54c-299">この値を割り当てる場合は、PrimarySMTPAddress を割り当てまたは割り当て中か、この値によって PrimarySMTPAddress が設定され、移動エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-299">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span>
      - <span data-ttu-id="ed54c-300">移行元メールボックスからターゲット MailUser に従来の smtp プロキシ アドレスを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-300">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="ed54c-301">たとえば、テナント オブジェクトの MEU contoso.com を維持 fabrikam.onmicrosoft.com できません)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-301">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="ed54c-302">ドメインは、1 つの Azure ADまたはExchange Onlineにのみ関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="ed54c-302">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>

     <span data-ttu-id="ed54c-303">MailUser **オブジェクト** の例:</span><span class="sxs-lookup"><span data-stu-id="ed54c-303">Example **target** MailUser object:</span></span>

     |<span data-ttu-id="ed54c-304">属性</span><span class="sxs-lookup"><span data-stu-id="ed54c-304">Attribute</span></span>|<span data-ttu-id="ed54c-305">値</span><span class="sxs-lookup"><span data-stu-id="ed54c-305">Value</span></span>|
     |---|---|
     |<span data-ttu-id="ed54c-306">エイリアス</span><span class="sxs-lookup"><span data-stu-id="ed54c-306">Alias</span></span>|<span data-ttu-id="ed54c-307">LaraN</span><span class="sxs-lookup"><span data-stu-id="ed54c-307">LaraN</span></span>|
     |<span data-ttu-id="ed54c-308">RecipientType</span><span class="sxs-lookup"><span data-stu-id="ed54c-308">RecipientType</span></span>|<span data-ttu-id="ed54c-309">MailUser</span><span class="sxs-lookup"><span data-stu-id="ed54c-309">MailUser</span></span>|
     |<span data-ttu-id="ed54c-310">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="ed54c-310">RecipientTypeDetails</span></span>|<span data-ttu-id="ed54c-311">MailUser</span><span class="sxs-lookup"><span data-stu-id="ed54c-311">MailUser</span></span>|
     |<span data-ttu-id="ed54c-312">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="ed54c-312">UserPrincipalName</span></span>|<span data-ttu-id="ed54c-313">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-313">LaraN@northwintraders.onmicrosoft.com</span></span>|
     |<span data-ttu-id="ed54c-314">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="ed54c-314">PrimarySmtpAddress</span></span>|<span data-ttu-id="ed54c-315">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-315">Lara.Newton@northwind.com</span></span>|
     |<span data-ttu-id="ed54c-316">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="ed54c-316">ExternalEmailAddress</span></span>|<span data-ttu-id="ed54c-317">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-317">SMTP:LaraN@contoso.onmicrosoft.com</span></span>|
     |<span data-ttu-id="ed54c-318">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="ed54c-318">ExchangeGuid</span></span>|<span data-ttu-id="ed54c-319">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="ed54c-319">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>|
     |<span data-ttu-id="ed54c-320">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="ed54c-320">LegacyExchangeDN</span></span>|<span data-ttu-id="ed54c-321">/o=First Organization/ou=Exchangeグループ</span><span class="sxs-lookup"><span data-stu-id="ed54c-321">/o=First Organization/ou=Exchange Administrative Group</span></span>|
     ||<span data-ttu-id="ed54c-322">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="ed54c-322">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>|
     |<span data-ttu-id="ed54c-323">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="ed54c-323">EmailAddresses</span></span>|<span data-ttu-id="ed54c-324">x500:/o=First Organization/ou=Exchange 管理グループ (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="ed54c-324">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>|
     ||<span data-ttu-id="ed54c-325">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="ed54c-325">7273f1f9-Lara</span></span>|
     ||<span data-ttu-id="ed54c-326">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-326">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>|
     ||<span data-ttu-id="ed54c-327">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-327">SMTP:Lara.Newton@northwind.com</span></span>|
     |||

     <span data-ttu-id="ed54c-328">ソース **メールボックス オブジェクト** の例:</span><span class="sxs-lookup"><span data-stu-id="ed54c-328">Example **source** Mailbox object:</span></span>

     |<span data-ttu-id="ed54c-329">属性</span><span class="sxs-lookup"><span data-stu-id="ed54c-329">Attribute</span></span>|<span data-ttu-id="ed54c-330">値</span><span class="sxs-lookup"><span data-stu-id="ed54c-330">Value</span></span>|
     |---|---|
     |<span data-ttu-id="ed54c-331">エイリアス</span><span class="sxs-lookup"><span data-stu-id="ed54c-331">Alias</span></span>|<span data-ttu-id="ed54c-332">LaraN</span><span class="sxs-lookup"><span data-stu-id="ed54c-332">LaraN</span></span>|
     |<span data-ttu-id="ed54c-333">RecipientType</span><span class="sxs-lookup"><span data-stu-id="ed54c-333">RecipientType</span></span>|<span data-ttu-id="ed54c-334">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="ed54c-334">UserMailbox</span></span>|
     |<span data-ttu-id="ed54c-335">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="ed54c-335">RecipientTypeDetails</span></span>|<span data-ttu-id="ed54c-336">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="ed54c-336">UserMailbox</span></span>|
     |<span data-ttu-id="ed54c-337">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="ed54c-337">UserPrincipalName</span></span>|<span data-ttu-id="ed54c-338">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-338">LaraN@contoso.onmicrosoft.com</span></span>|
     |<span data-ttu-id="ed54c-339">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="ed54c-339">PrimarySmtpAddress</span></span>|<span data-ttu-id="ed54c-340">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-340">Lara.Newton@contoso.com</span></span>|
     |<span data-ttu-id="ed54c-341">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="ed54c-341">ExchangeGuid</span></span>|<span data-ttu-id="ed54c-342">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="ed54c-342">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>|
     |<span data-ttu-id="ed54c-343">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="ed54c-343">LegacyExchangeDN</span></span>|<span data-ttu-id="ed54c-344">/o=First Organization/ou=Exchangeグループ</span><span class="sxs-lookup"><span data-stu-id="ed54c-344">/o=First Organization/ou=Exchange Administrative Group</span></span>|
     ||<span data-ttu-id="ed54c-345">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="ed54c-345">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>|
     |<span data-ttu-id="ed54c-346">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="ed54c-346">EmailAddresses</span></span>|<span data-ttu-id="ed54c-347">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-347">smtp:LaraN@contoso.onmicrosoft.com</span></span>
     ||<span data-ttu-id="ed54c-348">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed54c-348">SMTP:Lara.Newton@contoso.com</span></span>|
     |||

   - <span data-ttu-id="ed54c-349">ハイブリッド書き込みバックに追加Exchange属性が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-349">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="ed54c-350">含まれていない場合は、含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-350">If not, they should be included.</span></span>
   - <span data-ttu-id="ed54c-351">msExchBlockedSendersHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-351">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="ed54c-352">msExchSafeRecipientsHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-352">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="ed54c-353">msExchSafeSendersHash – クライアントからオンプレミスの Active Directory にオンラインセーフでブロックされた送信者データを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-353">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="ed54c-354">ソース メールボックスが LitigationHold に設定され、ソース メールボックスの回復可能なアイテムのサイズがデータベースの既定値 (30 GB) よりも大きい場合、ターゲット クォータがソース メールボックスのサイズより小さいので、移動は続行されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-354">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="ed54c-355">ターゲット MailUser オブジェクトを更新して、ELC メールボックス フラグをソース環境からターゲットに移行できます。これにより、ターゲット システムは MailUser のクォータを 100 GB に拡張し、ターゲットへの移動を許可します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-355">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="ed54c-356">ELC フラグをスタンプするコマンドはテナント管理者に公開されないので、これらの手順は Azure AD Connect を実行するハイブリッド ID でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-356">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed54c-357">サンプル – 現在、保証なし</span><span class="sxs-lookup"><span data-stu-id="ed54c-357">SAMPLE – AS IS, NO WARRANTY</span></span>
    >
    > <span data-ttu-id="ed54c-358">このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory (ADUser オブジェクトにスタンプを押す) の両方への接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="ed54c-358">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="ed54c-359">ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-359">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="ed54c-360">これにより、宛先アカウントのゴミ箱のサイズが 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-360">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. <span data-ttu-id="ed54c-361">ハイブリッド以外のターゲット テナントは、次のコマンドを実行して MailUser オブジェクトの訴訟ホールドを有効にし、クォータを 100 GB に増やして、移行前に MailUsers の回復可能なアイテム フォルダーのクォータを変更できます。 `Set-MailUser -EnableLitigationHoldForMigration $TRUE`</span><span class="sxs-lookup"><span data-stu-id="ed54c-361">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="ed54c-362">これは、ハイブリッドのテナントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-362">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="ed54c-363">ターゲット組織のユーザーは、組織に適用可能な適切なサブスクリプションExchange Onlineライセンスを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-363">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="ed54c-364">メールボックスの移動の前にライセンスを適用できますが、対象の MailUser が ExchangeGUID とプロキシ アドレスで適切に設定されている場合にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-364">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="ed54c-365">ExchangeGUID を適用する前にライセンスを適用すると、新しいメールボックスがターゲット組織にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-365">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed54c-366">Mailbox オブジェクトまたは MailUser オブジェクトにライセンスを適用すると、すべての SMTP タイプの proxyAddresses がスクラブされ、検証済みのドメインだけが Exchange EmailAddresses 配列に含まれるか確認されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-366">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span>

5. <span data-ttu-id="ed54c-367">ターゲットの MailUser に、ソース ExchangeGuid と一致しない以前の ExchangeGuid が存在しなかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-367">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="ed54c-368">これは、ターゲット MEU が以前にメールボックスのライセンスを取得し、Exchange Onlineされている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-368">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="ed54c-369">ターゲットの MailUser が以前に ExchangeGuid のライセンスを取得していたか、ソース ExchangeGuid と一致しない ExchangeGuid を持っていた場合は、クラウド MEU のクリーンアップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-369">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="ed54c-370">これらのクラウド MEUs では、実行できます `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` 。</span><span class="sxs-lookup"><span data-stu-id="ed54c-370">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="ed54c-371">このプロセスは不可逆的です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-371">This process is irreversible.</span></span> <span data-ttu-id="ed54c-372">オブジェクトに softDeleted メールボックスがある場合、この時点以降は復元できません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-372">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="ed54c-373">ただし、クリアすると、正しい ExchangeGuid をターゲット オブジェクトに同期し、MRS は新しく作成されたターゲット メールボックスにソース メールボックスを接続します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-373">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="ed54c-374">(新しいパラメーターに関する EHLO ブログを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-374">(Reference EHLO blog on the new parameter.)</span></span>

    <span data-ttu-id="ed54c-375">このコマンドを使用して、以前メールボックスだったオブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-375">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="ed54c-376">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-376">Here is an example.</span></span>

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize

    Name       PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails
    ----       ---------------------------- ------------- --------------------
    John       UserMailbox                  MailUser      MailUser
    ```

    <span data-ttu-id="ed54c-377">このコマンドを使用して、削除済みメールボックスを消去します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-377">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="ed54c-378">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-378">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm
    Are you sure you want to perform this action?
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.
    Do you want to continue?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="ed54c-379">メールボックスの移行を実行する</span><span class="sxs-lookup"><span data-stu-id="ed54c-379">Perform mailbox migrations</span></span>

<span data-ttu-id="ed54c-380">テナント間の移行Exchange移行は、移行バッチとしてターゲット テナントから開始されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-380">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="ed54c-381">これは、オンプレミスからオンプレミスへの移行時にオンボーディング移行バッチがExchangeに似Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ed54c-381">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span>

### <a name="create-migration-batches"></a><span data-ttu-id="ed54c-382">移行バッチの作成</span><span class="sxs-lookup"><span data-stu-id="ed54c-382">Create Migration batches</span></span>

<span data-ttu-id="ed54c-383">移動を開始する移行バッチ コマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-383">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!NOTE]
> <span data-ttu-id="ed54c-384">CSV ファイルの電子メール アドレスは、ソース テナントではなく、ターゲット テナントで指定された電子メール アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-384">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="ed54c-385">移行バッチの申請は、クロステナント オプションを選択Exchange管理センターからサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-385">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="ed54c-386">オンプレミスの MailUsers を更新する</span><span class="sxs-lookup"><span data-stu-id="ed54c-386">Update on-premises MailUsers</span></span>

<span data-ttu-id="ed54c-387">メールボックスがソースからターゲットに移動したら、オンプレミスのメール ユーザー (ソースとターゲットの両方) が新しい targetAddress で更新されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-387">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="ed54c-388">例では、移動で使用される targetDeliveryDomain **は次** contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-388">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="ed54c-389">この targetAddress を使用してメール ユーザーを更新します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-389">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ed54c-390">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ed54c-390">Frequently asked questions</span></span>

<span data-ttu-id="ed54c-391">**移動後に、オンプレミスのソースで RemoteMailboxes を更新する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-391">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="ed54c-392">はい、ソース テナント メールボックスがターゲット テナントに移動するときに、ソースのオンプレミス ユーザーの targetAddress (RemoteRoutingAddress/ExternalEmailAddress) を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-392">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="ed54c-393">メール ルーティングは、異なる targetAddresses を持つ複数のメール ユーザー間の参照に従う場合があります。メール ユーザーの空き時間情報の参照はメールボックス ユーザーの場所をターゲットにしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-393">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="ed54c-394">空き時間情報の参照は、複数のリダイレクトを追跡しない。</span><span class="sxs-lookup"><span data-stu-id="ed54c-394">Free/Busy lookups will not chase multiple redirects.</span></span>

<span data-ttu-id="ed54c-395">**会議Teamsテナント間で移行しますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-395">**Do Teams meetings migrate cross-tenant?**</span></span>

<span data-ttu-id="ed54c-396">ただし、アイテムがクロステナントを移行Teams場合、会議 URL は更新されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-396">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="ed54c-397">URL はターゲット テナントで無効になりますので、会議を削除して再作成Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-397">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="ed54c-398">**チャット フォルダー Teamsクロステナントを移行しますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-398">**Does the Teams chat folder content migrate cross-tenant?**</span></span>

<span data-ttu-id="ed54c-399">いいえ、Teamsフォルダーのコンテンツはクロステナントを移行できません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-399">No, the Teams chat folder content does not migrate cross-tenant.</span></span>

<span data-ttu-id="ed54c-400">**オンボーディングとオフボーディングの移動ではなく、テナント間の移動である移動を確認する方法**</span><span class="sxs-lookup"><span data-stu-id="ed54c-400">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="ed54c-401">パラメーターを `-flags` 使用します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-401">Use the `-flags` parameter.</span></span> <span data-ttu-id="ed54c-402">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-402">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

<span data-ttu-id="ed54c-403">**テストで使用する属性をコピーするためのスクリプトの例を提供できますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-403">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!NOTE]
> <span data-ttu-id="ed54c-404">サンプル – 現在、保証なし</span><span class="sxs-lookup"><span data-stu-id="ed54c-404">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="ed54c-405">このスクリプトは、ソース メールボックス (ソース値を取得する) とターゲットのオンプレミス Active Directory ドメイン サービス (ADUser オブジェクトにスタンプを押す) の両方への接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="ed54c-405">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="ed54c-406">ソースで訴訟または単一アイテムの回復が有効になっている場合は、コピー先アカウントでこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-406">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="ed54c-407">これにより、宛先アカウントのゴミ箱のサイズが 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-407">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit"
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

#################################################################
#Copy the file $outfile to the desktop of the target on-premises
#then run the below to create MEU in Target
#################################################################
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

#################################################################
# On AADSync machine, run AADSync
#################################################################
Start-ADSyncSyncCycle

#AADSync and FWDSync will create the target MEUs in the Target tenant
```

<span data-ttu-id="ed54c-408">**使用メールボックスの移動後Outlook 1 日目にアクセスする方法**</span><span class="sxs-lookup"><span data-stu-id="ed54c-408">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="ed54c-409">1 つのテナントだけがドメインを所有できるので、メールボックスの移動が完了すると、以前のプライマリ SMTPAddress はターゲット テナントのユーザーに関連付けされません。新しいテナントに関連付けられているドメインのみ。</span><span class="sxs-lookup"><span data-stu-id="ed54c-409">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="ed54c-410">Outlook新しい UPN を使用してサービスに対する認証を行い、Outlook プロファイルは、ターゲット システム内のメールボックスと一致するレガシ プライマリ SMTPAddress を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-410">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="ed54c-411">従来のアドレスがターゲットシステムに含されていないので、Outlook プロファイルは新しく移動されたメールボックスを見つけるために接続されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-411">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span>

<span data-ttu-id="ed54c-412">この初期展開では、ユーザーは新しい UPN、プライマリ SMTP アドレスを使用してプロファイルを再構築し、OST コンテンツを再同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-412">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span>

> [!NOTE]
> <span data-ttu-id="ed54c-413">完了のためにユーザーをバッチ処理する場合は、必要に応じて計画します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-413">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="ed54c-414">クライアント プロファイルが作成され、後続の OST ファイルと OAB ファイルがクライアントにダウンロードOutlookネットワーク使用率と容量を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-414">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span>

<span data-ttu-id="ed54c-415">**テナント間Exchangeを設定または完了するには、RBAC の役割を構成する必要がある役割を説明します。**</span><span class="sxs-lookup"><span data-stu-id="ed54c-415">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>

<span data-ttu-id="ed54c-416">メールボックスの移動を実行する際の委任された職務の前提に基づく役割のマトリックスがあります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-416">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="ed54c-417">現在、2 つの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-417">Currently, two roles are required:</span></span>

- <span data-ttu-id="ed54c-418">最初の役割は、テナント/組織の境界にコンテンツを移動または外に移動する権限を確立する 1 回のセットアップ タスクです。</span><span class="sxs-lookup"><span data-stu-id="ed54c-418">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="ed54c-419">組織の管理からデータを移動すると、すべての企業にとって重要な懸念事項となります。組織管理者 (OrgAdmin) の最も高い割り当てられた役割を選択しました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-419">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="ed54c-420">この役割は、-MailboxMoveCapability をリモート組織で定義する新しい OrganizationRelationship を変更またはセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-420">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="ed54c-421">MailboxMoveCapability 設定を変更できるのは OrgAdmin のみですが、OrganizationRelationhip の他の属性はフェデレーション共有管理者が管理できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-421">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span>

- <span data-ttu-id="ed54c-422">実際の移動コマンドを実行する役割は、下位レベルの関数に委任できます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-422">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="ed54c-423">メールボックスの移動の役割には、パラメーターを使用してメールボックスを組織の中または外に移動する機能が割り当 `-RemoteTenant` てられます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-423">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>

<span data-ttu-id="ed54c-424">**変換されたメールボックスの targetAddress (TargetDeliveryDomain) に選択されている SMTP アドレスを (MailUser 変換に) ターゲットにする方法を説明します。**</span><span class="sxs-lookup"><span data-stu-id="ed54c-424">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>

<span data-ttu-id="ed54c-425">Exchangeのメール アドレス (proxyAddress) を照合して MailUser に変換するときに、MRS を使用して移動する場合は、元のソース メールボックスの targetAddress を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-425">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="ed54c-426">このプロセスは、move コマンドに渡される -TargetDeliveryDomain 値を受け取り、ターゲット側のそのドメインの一致するプロキシをチェックします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-426">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="ed54c-427">一致を見つけると、一致する proxyAddress を使用して、変換されたメールボックス (現在の MailUser) オブジェクトに ExternalEmailAddress (targetAddress) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-427">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>

<span data-ttu-id="ed54c-428">**メールボックスのアクセス許可の移行方法**</span><span class="sxs-lookup"><span data-stu-id="ed54c-428">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="ed54c-429">メールボックスのアクセス許可には、代理送信とメールボックス アクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-429">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span>

- <span data-ttu-id="ed54c-430">Send On Behalf Of (AD:publicDelegates) は、代理人としてユーザーのメールボックスにアクセスできる受信者の DN を格納します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-430">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="ed54c-431">この値は Active Directory に格納され、現在はメールボックスの移行の一部として移動されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-431">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="ed54c-432">ソース メールボックスに publicDelegates が設定されている場合は、MEU からメールボックスへの変換が実行によってターゲット環境で完了したら、ターゲット メールボックスの publicDelegates を再サンプリングする `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-432">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span>

- <span data-ttu-id="ed54c-433">メールボックスに格納されているメールボックスのアクセス許可は、プリンシパルと代理人の両方がターゲット システムに移動すると、メールボックスと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-433">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="ed54c-434">たとえば、ユーザーがTestUser_7に FullAccess が付与TestUser_8のメールボックスに SourceCompany.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-434">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="ed54c-435">メールボックスの移動が完了すると、TargetCompany.onmicrosoft.com ディレクトリに同じアクセス許可が設定されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-435">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="ed54c-436">ソース テナントとターゲット テナントの両方TestUser_7 *Get-MailboxPermission* を使用する例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-436">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="ed54c-437">Exchangeコマンドレットには、ソースとターゲットのプレフィックスが付けされます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-437">Exchange cmdlets are prefixed with source and target accordingly.</span></span>

<span data-ttu-id="ed54c-438">移動前のメールボックスアクセス許可の出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-438">Here's an example of the output of the mailbox permission before a move.</span></span>

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```

<span data-ttu-id="ed54c-439">移動後のメールボックスアクセス許可の出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-439">Here's an example of the output of the mailbox permission after the move.</span></span>

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```

> [!NOTE]
> <span data-ttu-id="ed54c-440">テナント間のメールボックスと予定表のアクセス許可はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-440">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="ed54c-441">プリンシパルと代理人を統合移動バッチに整理して、接続されているこれらのメールボックスがソース テナントから同時に移行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-441">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span>

<span data-ttu-id="ed54c-442">**移行を有効にするには、どの X500 プロキシをターゲットの MailUser プロキシ アドレスに追加する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-442">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>

<span data-ttu-id="ed54c-443">テナント間メールボックスの移行では、ソース メールボックス オブジェクトの LegacyExchangeDN 値を、ターゲット MailUser オブジェクトの x500 メール アドレスとしてスタンプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-443">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>

<span data-ttu-id="ed54c-444">例:</span><span class="sxs-lookup"><span data-stu-id="ed54c-444">Example:</span></span>

```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!NOTE]
> <span data-ttu-id="ed54c-445">この X500 プロキシに加えて、ソース内のメールボックスからすべての X500 プロキシをターゲットのメールボックスにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-445">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>

<span data-ttu-id="ed54c-446">**移動が機能しない場合は、どこでトラブルシューティングを開始しますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-446">**Where do I start troubleshooting if moves do not work?**</span></span>

<span data-ttu-id="ed54c-447">まず、次のVerifySetup.ps1スクリプトを実行[しGitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview)を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-447">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="ed54c-448">次に、ターゲット テナントでVerifySetup.ps1例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-448">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="ed54c-449">次に、ソース テナントで実行VerifySetup.ps1 eExample を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-449">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="ed54c-450">**ソーステナントとターゲット テナントは同じドメイン名を使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-450">**Can the source and target tenant utilize the same domain name?**</span></span>

<span data-ttu-id="ed54c-451">いいえ。</span><span class="sxs-lookup"><span data-stu-id="ed54c-451">No.</span></span> <span data-ttu-id="ed54c-452">ソーステナントとターゲットテナントのドメイン名は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-452">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="ed54c-453">たとえば、ユーザーのソース ドメインと contoso.com のターゲット ドメイン fourthcoffee.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-453">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="ed54c-454">**共有メールボックスは移動し、引き続き機能しますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-454">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="ed54c-455">はい、ただし、次の記事の説明に従ってストアのアクセス許可のみを保持します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-455">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="ed54c-456">Microsoft Docs |ユーザー内の受信者のアクセス許可をExchange Online</span><span class="sxs-lookup"><span data-stu-id="ed54c-456">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="ed54c-457">Microsoft サポート |専用のメールボックスExchangeアクセスOutlookを付与するOffice 365方法</span><span class="sxs-lookup"><span data-stu-id="ed54c-457">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="ed54c-458">**Azure Key Vault が必要な場合と、トランザクションが行われた場合**</span><span class="sxs-lookup"><span data-stu-id="ed54c-458">**Is Azure Key Vault required and when are transactions made?**</span></span>

<span data-ttu-id="ed54c-459">はい、移行を承認するために Key Vault を使用して証明書を格納するには、Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-459">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="ed54c-460">ユーザー名 & パスワードを使用してソースに対する認証を行うオンボード移行とは異なり、テナント間メールボックスの移行では OAuth とこの証明書がシークレット/資格情報として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-460">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="ed54c-461">Key Vault へのアクセスは、移行の開始時と終了時に 1 回、増分同期時には 24 時間に 1 回アクセスされるので、すべてのメールボックス移行を通じて維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-461">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="ed54c-462">AKV のコスト計算の詳細については、こちらを参照 [してください](https://azure.microsoft.com/en-us/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="ed54c-462">You can review AKV costing details [here](https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>

<span data-ttu-id="ed54c-463">**バッチに関する推奨事項はありますか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-463">**Do you have any recommendations for batches?**</span></span>

<span data-ttu-id="ed54c-464">バッチあたりのメールボックス数は 2000 を超えないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ed54c-464">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="ed54c-465">同期中にエンド ユーザーに影響が出ない場合は、カットオーバー日の 2 週間前にバッチを送信することを強く推奨します。50,000 を超えるメールボックスの数量に関するガイダンスが必要な場合は、crosstenantmigrationpreview@service.microsoft.com のエンジニアリング フィードバック配布リストにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-465">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="ed54c-466">**顧客キーでサービス暗号化を使用する場合は、**</span><span class="sxs-lookup"><span data-stu-id="ed54c-466">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="ed54c-467">メールボックスは移動前に復号化されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-467">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="ed54c-468">顧客キーがまだ必要な場合は、ターゲット テナントで顧客キーが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-468">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="ed54c-469">詳細 [については、](../compliance/customer-key-overview.md) こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed54c-469">See [here](../compliance/customer-key-overview.md) for more information.</span></span>

<span data-ttu-id="ed54c-470">**推定移行時間は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ed54c-470">**What is the estimated migration time?**</span></span>

<span data-ttu-id="ed54c-471">移行を計画する際に役立つ、次[](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times)の表に、メールボックスの一括移行または個々の移行が完了すると予想される場合のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-471">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="ed54c-472">これらの見積もりは、以前の顧客移行のデータ分析に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="ed54c-472">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="ed54c-473">すべての環境が一意なので、正確な移行速度は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-473">Because every environment is unique, your exact migration velocity may vary.</span></span>

<span data-ttu-id="ed54c-474">この機能は現在プレビュー中であり、SLA および該当するサービス レベルは、この機能のプレビュー状態の間、パフォーマンスや可用性の問題には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ed54c-474">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ed54c-475">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ed54c-475">Known issues</span></span>

- <span data-ttu-id="ed54c-476">**問題: 自動拡張アーカイブを移行できません。**</span><span class="sxs-lookup"><span data-stu-id="ed54c-476">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="ed54c-477">テナント間移行機能は、特定のユーザーのプライマリ メールボックスとアーカイブ メールボックスの移行をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-477">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="ed54c-478">ただし、ソース内のユーザーが自動拡張アーカイブ (複数のアーカイブ メールボックスを意味する) を持つ場合、この機能は追加のアーカイブを移行できず、失敗する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-478">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="ed54c-479">**問題: 所有されていない smtp proxyAddress ブロック MRS がバックグラウンドを移動するクラウド MailUsers。**</span><span class="sxs-lookup"><span data-stu-id="ed54c-479">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="ed54c-480">ターゲット テナントの MailUser オブジェクトを作成する場合は、すべての SMTP プロキシ アドレスがターゲット テナント組織に属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-480">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="ed54c-481">ローカル テナントに属していないターゲット メール ユーザーに SMTP proxyAddress が存在する場合、MailUser からメールボックスへの変換は防止されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-481">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="ed54c-482">これは、メールボックス オブジェクトが、テナントが権限を持つドメイン (テナントが要求するドメイン) からのみメールを送信できるという保証が原因です。</span><span class="sxs-lookup"><span data-stu-id="ed54c-482">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span>

  - <span data-ttu-id="ed54c-483">Azure AD Connect を使用してオンプレミスからユーザーを同期する場合は、メールボックスが存在するソース テナント (laran@contoso.onmicrosoft.com) を指す ExternalEmailAddress を使用してオンプレミスの MailUser オブジェクトをプロビジョニングし、PrimarySMTPAddress をターゲット テナント (Lara.Newton@northwind.com) に存在するドメインとしてスタンプします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-483">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="ed54c-484">これらの値はテナントに同期され、適切なメール ユーザーがプロビジョニングされ、移行の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="ed54c-484">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="ed54c-485">オブジェクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-485">An example object is shown here.</span></span>

    ```powershell
    target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses
    ExternalEmailAddress               EmailAddresses
    --------------------               --------------
    SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
    ```

   > [!NOTE]
   > <span data-ttu-id="ed54c-486">電子 *contoso.onmicrosoft.com* アドレス *が* EmailAddresses/proxyAddresses 配列に存在しない。</span><span class="sxs-lookup"><span data-stu-id="ed54c-486">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="ed54c-487">**問題: "外部" プライマリ SMTP アドレスを持つ MailUser オブジェクトが変更/リセットされ、"内部" の会社が要求したドメインにリセットされる**</span><span class="sxs-lookup"><span data-stu-id="ed54c-487">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

  <span data-ttu-id="ed54c-488">MailUser オブジェクトは、ローカル以外のメールボックスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="ed54c-488">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="ed54c-489">テナント間メールボックスの移行の場合、MailUser オブジェクトを使用して、ソース メールボックス (ターゲット組織の観点から) またはターゲット メールボックス (ソース組織の観点から) を表します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-489">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="ed54c-490">MailUsers には、ディレクトリ内のメールボックス ユーザーの表示される SMTP アドレスを表す、実際のメールボックス (ProxyTest@fabrikam.onmicrosoft.com) の smtp アドレスと primarySMTP アドレスをポイントする ExternalEmailAddress (targetAddress) があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-490">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="ed54c-491">一部の組織では、プライマリ SMTP アドレスを外部 SMTP アドレスとして表示し、ローカル テナントが所有/検証したアドレスとしてではなく (fabrikam.com など)、外部 SMTP アドレスとして表示 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ed54c-491">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="ed54c-492">ただし、Exchange サービス プラン オブジェクトがライセンス操作を介して MailUser に適用されると、プライマリ SMTP アドレスが変更され、ローカル組織 (contoso.com) によって確認されたドメインとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-492">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="ed54c-493">次の 2 つの潜在的な理由があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-493">There are two potential reasons:</span></span>

  - <span data-ttu-id="ed54c-494">任意の Exchange サービス プランが MailUser に適用されると、Azure AD プロセスはプロキシ スクラブの適用を開始して、ローカル組織が別のテナントからメール、スプーフィング、またはメールを送信できないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-494">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="ed54c-495">これらのサービス プランを持つ受信者オブジェクト上の SMTP アドレスは、ローカル組織によってアドレスが確認されていない場合は削除されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-495">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="ed54c-496">例の場合と同様に、Fabikam.com ドメインは contoso.onmicrosoft.com テナントによって検証されないので、スクラブによってそのドメイン fabrikam.com されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-496">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="ed54c-497">移行前または移行後にこれらの外部ドメインを MailUser に保持する場合は、移行が完了した後、または移行前に移行プロセスを変更してライセンスを削除し、ユーザーが予期した外部ブランド化を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-497">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="ed54c-498">メールボックス オブジェクトがメール サービスに影響を与えずに適切にライセンスされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed54c-498">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="ed54c-499">テナント内の MailUser 上のサービス プランを削除するスクリプト Contoso.onmicrosoft.com 次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-499">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo
    ```

       <span data-ttu-id="ed54c-500">割り当てられた ServicePlans のセットの結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-500">Results in the set of ServicePlans assigned are shown here.</span></span>

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

    <span data-ttu-id="ed54c-501">ユーザーの PrimarySMTPAddress がスクラブされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-501">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="ed54c-502">ドメイン fabrikam.com は、テナントが所有していない contoso.onmicrosoft.com ディレクトリに表示されるプライマリ SMTP アドレスとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="ed54c-502">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

    <span data-ttu-id="ed54c-503">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed54c-503">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress
    ------------------        -------------------------               --------------------
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com
    ```

    - <span data-ttu-id="ed54c-504">msExchRemoteRecipientType が 8 (DeprovisionMailbox) に設定されている場合、ターゲット テナントに移行されるオンプレミスの MailUser の場合、Azure のプロキシ スクラブ ロジックは所有されていないドメインを削除し、primarySMTP を所有ドメインにリセットします。</span><span class="sxs-lookup"><span data-stu-id="ed54c-504">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="ed54c-505">オンプレミスの MailUser で msExchRemoteRecipientType をクリアすると、プロキシ スクラブ ロジックは適用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ed54c-505">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span>

      <span data-ttu-id="ed54c-506">以下は、サービス プランを含む、可能なサービス プランの完全Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ed54c-506">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

      |<span data-ttu-id="ed54c-507">名前</span><span class="sxs-lookup"><span data-stu-id="ed54c-507">Name</span></span>|
      |---|
      |<span data-ttu-id="ed54c-508">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="ed54c-508">Advanced eDiscovery Storage (500GB)</span></span>|
      |<span data-ttu-id="ed54c-509">顧客ロックボックス</span><span class="sxs-lookup"><span data-stu-id="ed54c-509">Customer Lockbox</span></span>|
      |<span data-ttu-id="ed54c-510">データ損失防止</span><span class="sxs-lookup"><span data-stu-id="ed54c-510">Data Loss Prevention</span></span>|
      |<span data-ttu-id="ed54c-511">Exchange Enterprise CAL サービス (EOP、DLP)</span><span class="sxs-lookup"><span data-stu-id="ed54c-511">Exchange Enterprise CAL Services (EOP, DLP)</span></span>|
      |<span data-ttu-id="ed54c-512">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="ed54c-512">Exchange Essentials</span></span>|
      |<span data-ttu-id="ed54c-513">ExchangeFoundation</span><span class="sxs-lookup"><span data-stu-id="ed54c-513">Exchange Foundation</span></span>|
      |<span data-ttu-id="ed54c-514">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="ed54c-514">Exchange Online (P1)</span></span>|
      |<span data-ttu-id="ed54c-515">Exchange Online (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="ed54c-515">Exchange Online (Plan 1)</span></span>|
      |<span data-ttu-id="ed54c-516">Exchange Online (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="ed54c-516">Exchange Online (Plan 2)</span></span>|
      |<span data-ttu-id="ed54c-517">Exchange Online 用の Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="ed54c-517">Exchange Online Archiving for Exchange Online</span></span>|
      |<span data-ttu-id="ed54c-518">Exchange Server 用の Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="ed54c-518">Exchange Online Archiving for Exchange Server</span></span>|
      |<span data-ttu-id="ed54c-519">Exchange Online非アクティブなユーザー アドオン</span><span class="sxs-lookup"><span data-stu-id="ed54c-519">Exchange Online Inactive User Add-on</span></span>|
      |<span data-ttu-id="ed54c-520">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="ed54c-520">Exchange Online Kiosk</span></span>|
      |<span data-ttu-id="ed54c-521">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="ed54c-521">Exchange Online Multi-Geo</span></span>|
      |<span data-ttu-id="ed54c-522">Exchange Online プラン 1</span><span class="sxs-lookup"><span data-stu-id="ed54c-522">Exchange Online Plan 1</span></span>|
      |<span data-ttu-id="ed54c-523">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="ed54c-523">Exchange Online POP</span></span>|
      |<span data-ttu-id="ed54c-524">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ed54c-524">Exchange Online Protection</span></span>|
      |<span data-ttu-id="ed54c-525">情報バリア</span><span class="sxs-lookup"><span data-stu-id="ed54c-525">Information Barriers</span></span>|
      |<span data-ttu-id="ed54c-526">Information Protection for Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="ed54c-526">Information Protection for Office 365 - Premium</span></span>|
      |<span data-ttu-id="ed54c-527">Information Protection for Office 365 - Standard</span><span class="sxs-lookup"><span data-stu-id="ed54c-527">Information Protection for Office 365 - Standard</span></span>|
      |<span data-ttu-id="ed54c-528">インサイト By MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="ed54c-528">Insights by MyAnalytics</span></span>|
      |<span data-ttu-id="ed54c-529">Microsoft 365高度な監査</span><span class="sxs-lookup"><span data-stu-id="ed54c-529">Microsoft 365 Advanced Auditing</span></span>|
      |<span data-ttu-id="ed54c-530">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="ed54c-530">Microsoft Bookings</span></span>|
      |<span data-ttu-id="ed54c-531">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="ed54c-531">Microsoft Business Center</span></span>|
      |<span data-ttu-id="ed54c-532">Microsoft MyAnalytics (フル機能)</span><span class="sxs-lookup"><span data-stu-id="ed54c-532">Microsoft MyAnalytics (Full)</span></span>|
      |<span data-ttu-id="ed54c-533">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ed54c-533">Office 365 Advanced eDiscovery</span></span>|
      |<span data-ttu-id="ed54c-534">Microsoft Defender for Office 365 (プラン 1)</span><span class="sxs-lookup"><span data-stu-id="ed54c-534">Microsoft Defender for Office 365 (Plan 1)</span></span>|
      |<span data-ttu-id="ed54c-535">Microsoft Defender for Office 365 (プラン 2)</span><span class="sxs-lookup"><span data-stu-id="ed54c-535">Microsoft Defender for Office 365 (Plan 2)</span></span>|
      |<span data-ttu-id="ed54c-536">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="ed54c-536">Office 365 Privileged Access Management</span></span>|
      |<span data-ttu-id="ed54c-537">プレミアム暗号化のOffice 365</span><span class="sxs-lookup"><span data-stu-id="ed54c-537">Premium Encryption in Office 365</span></span>|
      ||
