<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="955a2-101">必須: 組織のセキュリティおよび情報の保護レベルが定義されている</span><span class="sxs-lookup"><span data-stu-id="955a2-101">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="955a2-p101">組織に必要なセキュリティ レベルを計画し、決定している。これらのレベルでは、機密情報とそれに伴う必須データ セキュリティの最小限のセキュリティ レベルと強化するための追加のレベルが定義されます。</span><span class="sxs-lookup"><span data-stu-id="955a2-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="955a2-104">少なくとも 3 種類のセキュリティ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="955a2-104">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="955a2-105">基準</span><span class="sxs-lookup"><span data-stu-id="955a2-105">Baseline</span></span>
- <span data-ttu-id="955a2-106">機密</span><span class="sxs-lookup"><span data-stu-id="955a2-106">Sensitive</span></span>
- <span data-ttu-id="955a2-107">高度な規制</span><span class="sxs-lookup"><span data-stu-id="955a2-107">Highly regulated</span></span>

<span data-ttu-id="955a2-108">必要に応じて、[手順 1](../infoprotect-define-sec-infoprotect-levels.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="955a2-108">If needed, [Step 1](../infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="955a2-109">必須: Microsoft 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="955a2-109">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="955a2-110">次の [Office 365 セキュリティの強化](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)の設定が構成されました:</span><span class="sxs-lookup"><span data-stu-id="955a2-110">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="955a2-111">Microsoft 365 セキュリティセンターの脅威管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="955a2-111">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="955a2-112">その他の Exchange Online テナント レベルの設定</span><span class="sxs-lookup"><span data-stu-id="955a2-112">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="955a2-113">SharePoint 管理センターでのテナント レベルでの共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="955a2-113">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="955a2-114">Azure Active Directory (Azure AD) の設定</span><span class="sxs-lookup"><span data-stu-id="955a2-114">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="955a2-115">[SharePoint、OneDrive、Microsoft Teams 用の Office 365 Advanced Threat Protection (ATP) も有効にする](https://docs.microsoft.com/ja-JP/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。</span><span class="sxs-lookup"><span data-stu-id="955a2-115">Enable Office 365 Advanced Threat Protection for SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="955a2-116">必要に応じて、[手順 3](../infoprotect-configure-increased-security-office-365.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="955a2-116">If needed, [Step 3](../infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="955a2-117">省略可能: 環境全体で分類方法が構成されている</span><span class="sxs-lookup"><span data-stu-id="955a2-117">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="955a2-118">法務/コンプライアンス チームと協力して、組織のデータのガバナンスとセキュリティ ポリシーの適切な分類方法とラベリング方法を策定する。</span><span class="sxs-lookup"><span data-stu-id="955a2-118">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="955a2-119">これらのポリシーは、次の構成および展開に対応しています: </span><span class="sxs-lookup"><span data-stu-id="955a2-119">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="955a2-120">機密性の高いデータ タイプ</span><span class="sxs-lookup"><span data-stu-id="955a2-120">Sensitive data types</span></span>
- <span data-ttu-id="955a2-121">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="955a2-121">Retention labels</span></span>
- <span data-ttu-id="955a2-122">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="955a2-122">Sensitivity labels</span></span>
- <span data-ttu-id="955a2-123">Azure Information Protection のラベル</span><span class="sxs-lookup"><span data-stu-id="955a2-123">Azure Information Protection labels</span></span>

<span data-ttu-id="955a2-124">必要に応じて、[手順 2](../infoprotect-configure-classification.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="955a2-124">If needed, [Step 2](../infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="955a2-125">省略可能: Office 365 での特権アクセス管理の構成。</span><span class="sxs-lookup"><span data-stu-id="955a2-125">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="955a2-126">[Office 365 での特権アクセス管理を設定する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)トピックにある情報を使用し、トピックへのアクセス権限を有効にして、組織内に 1 つまたは複数の権限のあるアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="955a2-126">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="955a2-127">これらのポリシーを構成して、機密データや重要な構成設定へのアクセスを just-in-time アクセスで有効にします。</span><span class="sxs-lookup"><span data-stu-id="955a2-127">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="955a2-128">必要に応じて、[手順 4](../infoprotect-configure-privileged-access-management.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="955a2-128">If needed, [Step 4](../infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 
