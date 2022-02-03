---
title: ユーザーとデバイス アクセスの保護
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: ユーザーとデバイスのデータとサービスへのアクセスを保護しMicrosoft 365データ損失から保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9659d9117359fdb7a3264c244e128a1c20d0ec14
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62326689"
---
# <a name="protect-user-and-device-access"></a>ユーザーとデバイス アクセスの保護

データとサービスへのMicrosoft 365保護することは、サイバー攻撃から防御し、データ損失から保護するために重要です。 同じ保護は、環境内の他の SaaS アプリケーション、およびアプリケーション プロキシで公開されたオンプレミス アプリケーションAzure Active Directory適用できます。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項を確認する

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>手順 2: 管理者アカウントとアクセスを保護する
管理環境の管理に使用する管理Microsoft 365特権が含まれます。 これらは、ハッカーやサイバー攻撃者にとって貴重なターゲットです。 

まず、管理用に管理者アカウントのみを使用します。 管理者は、通常の非管理用に個別のユーザー アカウントを持ち、ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。

多要素認証と条件付きアクセスで管理者アカウントを保護します。 詳細については、「管理者アカウント [の保護」を参照してください](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。 

次に、特権アクセス管理を構成します。Office 365。 特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。 これは、機密データへの永続的なアクセスまたは重要な構成設定へのアクセスを持つ既存の特権管理者アカウントを使用する可能性のある侵害から組織を保護するのに役立ちます。

- [特権アクセス管理の概要](privileged-access-management-overview.md)
- [特権アクセス管理を構成する](privileged-access-management-configuration.md)

もう 1 つの推奨事項は、管理作業用に特別に構成されたワークステーションを使用する方法です。 これらは、管理タスクにのみ使用される専用デバイスです。 「 [特権アクセスのセキュリティ保護」を参照してください](/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最後に、テナントに 2 つ以上の緊急アクセス アカウントを作成することで、管理アクセスの不注意による影響を軽減できます。 「[緊急アクセス アカウントを管理する」を参照Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>手順 3: 推奨される ID とデバイス アクセス ポリシーを構成する
多要素認証 (MFA) と条件付きアクセス ポリシーは、侵害されたアカウントや不正アクセスを軽減するための強力なツールです。 一緒にテストされた一連のポリシーを実装することをお勧めします。 展開手順を含む詳細については、「 [Identity and device access configurations」を参照してください](../security/office-365-security/microsoft-365-policies-configurations.md)。

 これらのポリシーは、次の機能を実装します。
- Mult-factor 認証
- 条件付きアクセス
- Intune アプリ保護 (デバイスのアプリとデータ保護)
- Intune デバイス コンプライアンス
- Azure AD Identity Protection

Intune デバイスのコンプライアンスを実装するには、デバイスの登録が必要です。 デバイスを管理すると、環境内のリソースへのアクセスを許可する前に、デバイスが正常で準拠することを確認できます。 [「Intune での管理用デバイスの登録」を参照してください。](/mem/intune/user-help/enroll-windows-10-device)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>手順 4: デバイス アクセス SharePointポリシーを構成する

Microsoft では、デバイス アクセス制御を使用してSharePoint規制の厳しいコンテンツを使用して、サイト内のコンテンツを保護することを推奨します。 詳細については、「サイトとファイル[のセキュリティ保護に関するSharePoint推奨事項」を参照してください](../security/office-365-security/sharepoint-file-access-policies.md)。



