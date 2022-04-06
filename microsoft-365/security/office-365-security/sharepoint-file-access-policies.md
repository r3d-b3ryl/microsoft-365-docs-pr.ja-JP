---
title: セキュリティで保護されたドキュメントの推奨されるポリシー - Microsoft 365 for enterprise | Microsoft Docs
description: SharePoint ファイル アクセスをセキュリティで保護する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: dansimp
author: dansimp
manager: dansimp
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
ms.openlocfilehash: 6effe1ffefaf7faeb90258163c539cdddcec2679
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569999"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項

この記事では、SharePoint とOneDrive for Business を保護するために推奨されるゼロ トラスト ID とデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは[共通 ID およびデバイス アクセス ポリシー](identity-access-policies.md)に基づいています。

これらの推奨事項は、ニーズの粒度に基づいて適用可能な SharePoint ファイルのセキュリティと保護の 3 つの異なる層 (**出発点**、**企業**、および **特殊なセキュリティ**) に基づいています。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[概要](microsoft-365-policies-configurations.md)を参照してください。

このガイダンスの実装に加えて、エンタープライズおよび特殊なセキュリティ コンテンツに適切なアクセス許可を設定するなど、適切な量の保護を使用して SharePoint サイトを構成してください。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>一般的なポリシーを更新して SharePoint と OneDrive for Business を含める

次の図は、SharePoin tおよび OneDrive のファイルを保護するために、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png" alt-text="ポリシーへのアクセスを保護するためのポリシー更新プログラムの概要SharePoint" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png":::

共通ポリシーの作成時に SharePoint を含めた場合は、新しいポリシーを作成するだけで完了できます。 条件付きアクセスポリシーの場合、SharePoint には OneDrive が含まれています。

新しいポリシーは、指定した SharePoint サイトに特定のアクセス要件を適用することにより、エンタープライズおよび特殊なセキュリティ コンテンツのデバイス保護を実装します。

次の表に、SharePoint のレビューと更新または新規作成が必要なポリシーを示します。 共通ポリシーは、[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)の記事にある関連する構成手順にリンクしています。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|**開始点**|[サインインのリスクが *中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含めます。|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに SharePoint を含めます。|
||[アプリ データ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|推奨されるすべてのアプリがアプリのリストに含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。|
||[SharePoint でアプリによって適用される制限を使用する](#use-app-enforced-restrictions-in-sharepoint)|この新しいポリシーを追加します。 これにより、Azure Active Directory (Azure AD) は SharePoint で指定された設定を使用するようになります。 このポリシーはすべてのユーザーに適用されますが、SharePoint アクセス ポリシーに含まれるサイトへのアクセスにのみ影響します。|
|**エンタープライズ**|[サインインのリスクが *低*、*中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含めます。|
||[準拠した PC *と* モバイル デバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリのリストに SharePoint を含めます。|
||[SharePoint アクセス制御ポリシー](#sharepoint-access-control-policies): 非管理対象デバイスから特定の SharePoint サイトへのブラウザーのみのアクセスを許可します。|これにより、ファイルの編集およびダウンロードが防止されます。 PowerShell を使用してサイトを指定します。|
|**特殊なセキュリティ**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに SharePoint を含めます。|
||[SharePoint アクセス制御ポリシー](#use-app-enforced-restrictions-in-sharepoint): 非管理対象デバイスから特定の SharePoint サイトへのアクセスをブロックします。|PowerShell を使用してサイトを指定します。|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>SharePoint でアプリによって適用される制限を使用する

SharePoint でアクセス制御を実装すると、Azure AD で条件付きアクセス ポリシーが作成され、Azure AD で構成するポリシーを適用SharePoint。 既定では、このポリシーはすべてのユーザーに適用されますが、PowerShell を使用して指定したサイトへのアクセスは、PowerShell でアクセス制御を作成するときにのみSharePoint。 ポリシーは、特定のユーザー、グループ、またはサイトに対してスコープを設定することもできます。

このポリシーを構成するには、「[非管理対象デバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスを制限する」を参照してください。

## <a name="sharepoint-access-control-policies"></a>SharePoint アクセス制御ポリシー

Microsoft では、SharePoint サイトのコンテンツをエンタープライズで保護し、特殊なセキュリティ コンテンツをデバイスのアクセス制御で保護することをお勧めします。 これを行うには、保護のレベルと保護を適用するサイトを指定するポリシーを作成します。

- エンタープライズ サイト: ブラウザのみのアクセスを許可します。 これにより、ユーザーによるファイルの編集およびダウンロードが防止されます。
- 専用のセキュリティ サイト: 管理されていないデバイスからのアクセスをブロックします。

「[非管理対象デバイスからのアクセスを制御する](/sharepoint/control-access-from-unmanaged-devices)」の「特定の SharePoint サイト コレクションまたは OneDrive アカウントへのアクセスを制限する」を参照してください。

## <a name="how-these-policies-work-together"></a>これらのポリシーが連携する方法

SharePoint サイトのアクセス許可は通常、サイトへのアクセスに対するビジネス ニーズに基づいていることを理解することが重要です。 これらの権限はサイト所有者によって管理され、高度に動的なものにすることができます。 SharePoint デバイス アクセス ポリシーを使用すると、ユーザーが開始点、エンタープライズ、または特殊なセキュリティ保護に関連付けられた Azure AD グループに割り当てられているかどうかに関係なく、これらのサイトを確実に保護できます。

次の図は、SharePoint デバイス アクセス ポリシーがユーザーのサイトへのアクセスを保護する方法の例を示しています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png" alt-text="デバイス アクセス ポリシーがサイトSharePoint保護する方法の例" lightbox="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png":::

James には開始点の条件付きアクセス ポリシーが割り当てられていますが、エンタープライズまたは特殊なセキュリティ保護を備えた SharePoint サイトへのアクセスを許可できます。

- James が自分の PC を使用して、エンタープライズまたは特殊なセキュリティ保護のメンバーであるサイトにアクセスすると、アクセスが許可されます。
- James が自分の管理されていない電話を使用してメンバーであるエンタープライズ保護サイトにアクセスすると、このサイトに設定されたデバイスのアクセス許可ポリシーにより、エンタープライズ サイトへのブラウザのみのアクセスが許可されます。
- ジェームズが管理されていない電話を使用して、自分がメンバーである専用セキュリティ サイトにアクセスすると、このサイトに設定されているアクセスポリシーのためにブロックされます。 彼は自分のマネージド PC を使用してのみこのサイトにアクセスできます。

## <a name="next-step"></a>次の手順

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="手順 4 - クラウド アプリMicrosoft 365ポリシー" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::


次の条件付きアクセス ポリシーを構成する:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
