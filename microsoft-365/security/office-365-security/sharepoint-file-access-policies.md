---
title: 推奨されるセキュリティ保護されたドキュメント ポリシー - エンタープライズ向け Microsoft 365 |Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: a217970098ab88da286bb44a69845b6383a27bbc
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097176"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、推奨される ID ポリシーとデバイス アクセス ポリシーを実装して SharePoint と OneDrive for Business を保護する方法について説明します。 このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーに基っています](identity-access-policies.md)。

これらの推奨事項は、ニーズの粒度に基づいて適用できる SharePoint ファイルのセキュリティと保護の 3 つの異なる層に基づいており、ベースライン、機密、厳しく規制 **されています**。 これらのセキュリティ層、およびこれらの推奨事項で参照されている推奨クライアント オペレーティング システムの詳細については、概要を [参照してください](microsoft-365-policies-configurations.md)。

このガイダンスの実装に加えて、機密性の高い厳しく規制されたコンテンツに対する適切なアクセス許可の設定など、適切な保護を備えて SharePoint サイトを構成してください。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint と OneDrive for Business を含む一般的なポリシーの更新

SharePoint と OneDrive のファイルを保護するために、次の図は、共通の ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

共通ポリシーの作成時に SharePoint を含める場合は、新しいポリシーを作成する必要があります。 条件付きアクセス ポリシーの場合、SharePoint には OneDrive が含まれます。

新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することで、機密性の高い厳しく規制されたコンテンツのデバイス保護を実装します。

次の表に、SharePoint の確認と更新、または新規の作成に必要なポリシーを示します。 共通ポリシーは、共通 ID とデバイス アクセス ポリシーに関する記事に関連する構成手順 [にリンク](identity-access-policies.md) しています。

|保護レベル|Policies|詳細|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに SharePoint を含める。|
||[アプリ データ保護ポリシーの適用](identity-access-policies.md#apply-app-data-protection-policies)|推奨されるアプリすべてがアプリの一覧に含まれている必要があります。 各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウド アプリの一覧に SharePoint を含める。|
||[SharePoint でアプリによって適用される制限を使用する](#use-app-enforced-restrictions-in-sharepoint)|この新しいポリシーを追加します。 これにより、Azure Active Directory (Azure AD) に、SharePoint で指定された設定を使用するように指示します。 このポリシーはすべてのユーザーに適用されますが、SharePoint アクセス ポリシーに含まれるサイトへのアクセスにのみ影響します。|
|**機密**|[サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[準拠した PC とモバイル *デバイスが* 必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリの一覧に SharePoint を含める。|
||[SharePoint アクセス制御ポリシー](#sharepoint-access-control-policies): 非管理対象デバイスから特定の SharePoint サイトへのブラウザー専用アクセスを許可します。|これにより、ファイルの編集とダウンロードが防止されます。 PowerShell を使用してサイトを指定します。|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[SharePoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 非管理対象デバイスからの特定の SharePoint サイトへのアクセスをブロックします。|PowerShell を使用してサイトを指定します。|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>SharePoint でアプリによって適用される制限を使用する

SharePoint にアクセス制御を実装する場合は、Azure AD でこの条件付きアクセス ポリシーを作成して、SharePoint で構成したポリシーを適用するように Azure AD に伝える必要があります。 このポリシーはすべてのユーザーに適用されますが、SharePoint でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。

このポリシーを構成するには、「非管理対象デバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは [制限する」を参照してください](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。

## <a name="sharepoint-access-control-policies"></a>SharePoint アクセス制御ポリシー

デバイス アクセス制御を使用して、機密性の高い厳しく規制されたコンテンツを使用して SharePoint サイトのコンテンツを保護することを推奨します。 これを行うには、保護のレベルと、保護を適用するサイトを指定するポリシーを作成します。

- 機密性の高いサイト: ブラウザー専用アクセスを許可します。 これにより、ユーザーはファイルを編集およびダウンロードできます。
- 厳しく規制されたサイト: 非管理対象デバイスからのアクセスをブロックします。

非管理対象デバイスからのアクセスの制御の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」 [を参照してください](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)。

## <a name="how-these-policies-work-together"></a>これらのポリシーの組み合わせ

SharePoint サイトのアクセス許可は、通常、サイトへのアクセスに関するビジネス 上の必要性に基づくと理解することが重要です。 これらのアクセス許可はサイトの所有者によって管理され、動的にできます。 SharePoint デバイス アクセス ポリシーを使用すると、ベースライン、機密、または厳しく規制された保護に関連付けられている Azure AD グループにユーザーが割り当てられているかどうかに関係なく、これらのサイトを保護できます。

次の図は、SharePoint デバイス アクセス ポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。

[![SharePoint デバイス アクセス ポリシーがサイトを保護する方法の例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James には、ベースラインの条件付きアクセス ポリシーが割り当てらたっていますが、機密性の高い保護または厳しく規制された保護を持つ SharePoint サイトへのアクセス権を与えられる可能性があります。

- 彼が PC を使用するメンバーである機密性の高いサイトまたは厳しく規制されたサイトにアクセスする場合、彼の PC が準拠している限り、アクセスが許可されます。
- ベースライン ユーザーに許可されている非管理対象電話を使用するメンバーである機密性の高いサイトにアクセスする場合、このサイト用に構成されたデバイス アクセス ポリシーにより、機密サイトへのブラウザー専用アクセスを受け取る。
- 管理されていない電話を使用するメンバーである厳しく規制されたサイトにアクセスした場合、このサイトに対して構成されたアクセス ポリシーが原因でブロックされます。 このサイトには、管理対象の準拠 PC を使用してしかアクセスできません。

## <a name="next-step"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件に合ったアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
