---
title: ゲスト ユーザーと外部ユーザー B2B アクセスを許可するための ID ポリシーとデバイス アクセス ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: ゲストと外部ユーザーのアクセスを保護するための推奨される条件付きアクセスと関連ポリシーについて説明します。
ms.prod: m365-security
ms.topic: article
ms.author: dansimp
author: dansimp
audience: Admin
manager: Laurawi
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
- zerotrust-solution
- highpri
ms.technology: mdo
ms.openlocfilehash: 872d5e5fc7774a32619e637bdb6dceb6e07b324e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466901"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>ゲスト アクセスと B2B 外部ユーザー アクセスを許可するためのポリシー

この記事では、Azure Active Directory (Azure AD) Business-to-Business (B2B) アカウントを持つゲストと外部ユーザーにアクセスできるように、推奨されるゼロ トラスト ID とデバイス アクセス ポリシーを調整する方法について説明します。 このガイダンスは[共通 ID およびデバイス アクセス ポリシー](identity-access-policies.md)に基づいています。

これらの推奨事項は、保護の **開始点** レベルに適用するように設計されています。 ただし、 **エンタープライズ** および **特殊なセキュリティ** 保護に対する特定のニーズに基づいて推奨事項を調整することもできます。

Azure AD テナントで認証するための B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。 B2B ユーザーとそのアカウントは、条件付きアクセス ポリシーによって共有されるサービスやリソース (ファイルなど) にアクセスできます。

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>ゲストと外部ユーザー アクセスを許可および保護するための共通ポリシーの更新

次の図は、B2B ゲスト アクセスと外部ユーザー アクセスに対して、共通 ID ポリシーとデバイス アクセス ポリシー間で追加または更新するポリシーを示しています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png" alt-text="ゲスト アクセスを保護するためのポリシー更新プログラムの概要" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png":::

次の表に、作成および更新する必要があるポリシーを示します。 共通ポリシーは、[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)の記事にある関連する構成手順にリンクしています。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|**開始点**|[ゲストと外部ユーザーに対して常に MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|この新しいポリシーを作成し、次を構成します。 <ul><li>[ **割り当て] > [ユーザーとグループ] > [含める**] で [ **ユーザーとグループの選択**] を選択し、[ **すべてのゲスト ユーザーと外部ユーザー**] を選択します。</li><li>**[割り当て>条件>サインイン] では**、すべてのオプションをオフのままにして、常に多要素認証 (MFA) を適用します。</li></ul>|
||[サインインのリスクが *中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|ゲストと外部ユーザーを除外するには、このポリシーを変更します。|

条件付きアクセス ポリシーにゲストと外部ユーザーを含める、または除外するには、[ **割り当て>ユーザーとグループ>含める** または **除外** する] で、[ **すべてのゲスト ユーザーと外部ユーザー**] をオンにします。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png" alt-text="ゲストと外部ユーザーを除外するためのコントロール" lightbox="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png":::

## <a name="more-information"></a>詳細

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Microsoft Teams を使用したゲストと外部ユーザー アクセス

Microsoft Teams では、次のユーザーが定義されています。

- **ゲスト アクセス** では、チームのメンバーとして追加でき、チームの通信とリソースにアクセスできる Azure AD B2B アカウントが使用されます。

- **外部アクセス** は、B2B アカウントを持たない外部ユーザー向けです。 外部ユーザー アクセスには、招待、通話、チャット、会議が含まれますが、チーム メンバーシップとチームのリソースへのアクセスは含まれません。

詳細については、 [ゲストとチームの外部ユーザー アクセスの比較を](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)参照してください。

Teams の ID およびデバイス アクセス ポリシーのセキュリティ保護の詳細については、「 [Teams チャット、グループ、ファイルをセキュリティで保護するためのポリシーに関する推奨事項](teams-access-policies.md)」を参照してください。

### <a name="require-mfa-always-for-guest-and-external-users"></a>ゲストユーザーと外部ユーザーに対して常に MFA を要求する

このポリシーは、ホーム テナントで MFA に登録されているかどうかに関係なく、テナントに MFA を登録するようにゲストに求めます。 テナント内のリソースにアクセスする場合、ゲストと外部ユーザーはすべての要求に対して MFA を使用する必要があります。

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>ゲストと外部ユーザーをリスクベースの MFA から除外する

組織では、Azure AD Identity Protection を使用して B2B ユーザーにリスクベースのポリシーを適用できますが、ホーム ディレクトリに存在する ID が原因で、リソース ディレクトリに B2B コラボレーション ユーザー向けの Azure AD Identity Protection の実装に制限があります。 これらの制限により、Microsoft では、リスクベースの MFA ポリシーからゲストを除外し、これらのユーザーに常に MFA を使用するよう要求することをお勧めします。

詳細については、「 [B2B コラボレーション ユーザーの Identity Protection の制限事項](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。

### <a name="excluding-guests-and-external-users-from-device-management"></a>デバイス管理からゲストと外部ユーザーを除外する

デバイスを管理できる組織は 1 つだけです。 デバイスコンプライアンスを必要とするポリシーからゲストと外部ユーザーを除外しない場合、これらのポリシーはこれらのユーザーをブロックします。

## <a name="next-step"></a>次のステップ

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Microsoft 365 クラウド アプリとMicrosoft Defender for Cloud Appsのポリシー" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

次の条件付きアクセス ポリシーを構成する:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Defender for Cloud Apps](mcas-saas-access-policies.md)
 
