---
title: ユーザーとデバイス アクセスの保護
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 のデータとサービスへのユーザーとデバイスのアクセスを保護し、データ損失から保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8b6b266d037e8bbc185643e530bf7a2f6919038
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623710"
---
# <a name="protect-user-and-device-access"></a>ユーザーとデバイス アクセスの保護

Microsoft 365 のデータとサービスへのアクセスを保護することは、サイバー攻撃から保護し、データ損失を防ぐために非常に重要です。 同じ保護は、環境内の他の SaaS アプリケーションや、Azure Active Directory アプリケーション プロキシで公開されたオンプレミス アプリケーションにも適用できます。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項を確認する

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>手順 2: 管理者アカウントとアクセスを保護する

Microsoft 365 環境の管理に使用する管理アカウントには、管理者特権が含まれます。 これらは、ハッカーやサイバー攻撃の貴重なターゲットです。

管理者アカウントのみを管理に使用することから始めます。 管理者は、通常の非管理者用の別のユーザー アカウントを持ち、自分のジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。

多要素認証と条件付きアクセスを使用して管理者アカウントを保護します。 詳細については、「 [管理者アカウントの保護](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)」を参照してください。 

次に、Microsoft Purview Privileged Access Management を構成します。 特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。 機密データに永続的にアクセスしたり、重要な構成設定にアクセスしたりして、既存の特権管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。

- [特権アクセス管理の概要](privileged-access-management.md)
- [特権アクセス管理を構成する](privileged-access-management-configuration.md)

もう 1 つの最も重要な推奨事項は、特に管理作業用に構成されたワークステーションを使用することです。 これらは、管理タスクにのみ使用される専用デバイスです。 [特権アクセスのセキュリティ保護に関する説明を](/windows-server/identity/securing-privileged-access/securing-privileged-access)参照してください。

最後に、テナントに 2 つ以上の緊急アクセス アカウントを作成することで、管理アクセスの不注意による不足の影響を軽減できます。 [Azure AD での緊急アクセス アカウントの管理に関するページを](/azure/active-directory/users-groups-roles/directory-emergency-access)参照してください。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>手順 3: 推奨される ID ポリシーとデバイス アクセス ポリシーを構成する

多要素認証 (MFA) と条件付きアクセス ポリシーは、侵害されたアカウントや承認されていないアクセスから軽減するための強力なツールです。 一緒にテストされた一連のポリシーを実装することをお勧めします。 展開手順を含む詳細については、「 [ID とデバイスアクセスの構成」を](../security/office-365-security/microsoft-365-policies-configurations.md)参照してください。

 これらのポリシーでは、次の機能が実装されています。

- 多要素認証
- 条件付きアクセス
- Intune アプリ保護 (デバイスのアプリとデータ保護)
- Intune デバイス コンプライアンス
- Azure AD Identity Protection

デバイス コンプライアンスIntune実装するには、デバイスの登録が必要です。 デバイスを管理すると、環境内のリソースへのアクセスを許可する前に、デバイスが正常で準拠していることを確認できます。 [「Intuneでの管理用デバイスの登録](/mem/intune/user-help/enroll-windows-10-device)」を参照してください。

## <a name="step-4-configure-sharepoint-device-access-policies"></a>手順 4: SharePoint デバイス アクセス ポリシーを構成する

Microsoft では、デバイス アクセス制御を使用して、機密性の高い高度に規制されたコンテンツを含む SharePoint サイトのコンテンツを保護することをお勧めします。 詳細については、「 [SharePoint サイトとファイルをセキュリティで保護するためのポリシーの推奨事項](../security/office-365-security/sharepoint-file-access-policies.md)」を参照してください。
