---
title: 推奨されるセキュリティで保護されたドキュメント ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064468"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- SharePoint Online 


この記事では、SharePoint と OneDrive for Business を保護するために推奨される ID ポリシーとデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーを基にしています](identity-access-policies.md)。

これらの推奨事項は、ニーズの粒度に基づいて適用できる SharePoint ファイルのセキュリティと保護の 3 つの層に基づいて行います。ベースライン、機密性の高い、高度に規制 **されています**。 これらのセキュリティ層と、これらの推奨事項で参照される推奨クライアント オペレーティング システムの詳細については、「概要」 [を参照してください](microsoft-365-policies-configurations.md)。

このガイダンスの実装に加えて、機密性の高い規制が厳しいコンテンツに対して適切なアクセス許可を設定するなど、適切な保護を備えて SharePoint サイトを構成してください。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>SharePoint と OneDrive for Business を含む一般的なポリシーを更新する

SharePoint と OneDrive のファイルを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

共通ポリシーの作成時に SharePoint を含める場合は、新しいポリシーのみを作成する必要があります。 条件付きアクセス ポリシーの場合、SharePoint には OneDrive が含まれます。

新しいポリシーでは、指定した SharePoint サイトに特定のアクセス要件を適用することで、機密性の高い高度に規制されたコンテンツのデバイス保護を実装します。

次の表に、SharePoint のレビューと更新、または新しい作成を行う必要があるポリシーを示します。 共通ポリシーは、「共通 ID とデバイス アクセス ポリシー」の記事に関連付けられた構成 [手順にリンク](identity-access-policies.md) します。

|保護レベル|Policies|詳細情報|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに SharePoint を含める。|
||[APP データ保護ポリシーの適用](identity-access-policies.md#apply-app-data-protection-policies)|すべての推奨アプリがアプリの一覧に含まれているか確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウド アプリの一覧に SharePoint を含める。|
||[SharePoint でアプリに適用される制限を使用する](#use-app-enforced-restrictions-in-sharepoint)|この新しいポリシーを追加します。 これにより、Azure Active Directory (Azure AD) に、SharePoint で指定された設定を使用するように指示されます。 このポリシーはすべてのユーザーに適用されますが、SharePoint アクセス ポリシーに含まれるサイトへのアクセスにのみ影響します。|
|**機密**|[サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[準拠している PC とモバイル *デバイスを* 要求する](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリの一覧に SharePoint を含める。|
||[SharePoint アクセス制御ポリシー](#sharepoint-access-control-policies): 管理されていないデバイスから特定の SharePoint サイトへのブラウザー専用アクセスを許可します。|これにより、ファイルの編集とダウンロードが防止されます。 PowerShell を使用してサイトを指定します。|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含める。|
||[SharePoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 管理されていないデバイスからの特定の SharePoint サイトへのアクセスをブロックします。|PowerShell を使用してサイトを指定します。|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>SharePoint でのアプリによる制限の使用

SharePoint でアクセス制御を実装する場合は、Azure AD でこの条件付きアクセス ポリシーを作成して、SharePoint で構成したポリシーを適用するように Azure AD に伝える必要があります。 このポリシーはすべてのユーザーに適用されますが、SharePoint でアクセス制御を作成するときに PowerShell を使用して指定したサイトへのアクセスにのみ影響します。

このポリシーを構成するには、「管理されていないデバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは制限する」 [を参照してください](/sharepoint/control-access-from-unmanaged-devices)。

## <a name="sharepoint-access-control-policies"></a>SharePoint アクセス制御ポリシー

Microsoft では、デバイス アクセス制御を使用して、機密性の高い規制の高いコンテンツを使用して SharePoint サイト内のコンテンツを保護することを推奨します。 これを行うには、保護のレベルと保護を適用するサイトを指定するポリシーを作成します。

- 機密性の高いサイト: ブラウザー専用のアクセスを許可します。 これにより、ユーザーはファイルを編集およびダウンロードできます。
- 高度に規制されたサイト: 管理されていないデバイスからのアクセスをブロックします。

「管理されていないデバイスからのアクセスを制御する」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスをブロックまたは [制限する」を参照してください](/sharepoint/control-access-from-unmanaged-devices)。

## <a name="how-these-policies-work-together"></a>これらのポリシーの動作

SharePoint サイトのアクセス許可は、通常、サイトへのアクセスに対するビジネス上の必要性に基づいて行なう必要があります。 これらのアクセス許可は、サイトの所有者によって管理され、非常に動的な場合があります。 SharePoint デバイス アクセス ポリシーを使用すると、ベースライン保護、機密性の高い保護、または厳しく規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、これらのサイトを保護できます。

次の図は、SharePoint デバイス アクセス ポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。

[![SharePoint デバイス アクセス ポリシーがサイトを保護する方法の例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James には基準となる条件付きアクセス ポリシーが割り当て済みですが、機密性の高い保護または高度に規制された保護を備え、SharePoint サイトにアクセスできます。

- James が自分の PC を使用するメンバーである機密性の高い、または規制の厳しいサイトにアクセスした場合、自分の PC が準拠している限り、アクセスが許可されます。
- James が管理されていない電話を使用するメンバーである機密性の高いサイトにアクセスした場合、このサイト用に構成されたデバイス アクセス ポリシーにより、機密性の高いサイトへのブラウザー専用アクセスを受け取る必要があります。
- James が管理されていない電話を使用するメンバーである規制の厳しいサイトにアクセスすると、このサイト用に構成されたアクセス ポリシーが原因でブロックされます。 このサイトにアクセスできるのは、管理および準拠している PC を使用する場合のみです。

## <a name="next-step"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)