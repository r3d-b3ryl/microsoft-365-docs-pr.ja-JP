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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 データとサービスへのユーザーとデバイスのアクセスを保護し、データ損失から保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051699"
---
# <a name="protect-user-and-device-access"></a>ユーザーとデバイス アクセスの保護

Microsoft 365 のデータとサービスへのアクセスを保護することは、サイバー攻撃から防御し、データ損失から保護するために重要です。 同じ保護は、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーション プロキシで公開されたオンプレミス アプリケーションにも適用できます。
  
## <a name="step-1-review-recommendations"></a>手順 1: 推奨事項を確認する

Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>手順 2: 管理者アカウントとアクセスを保護する
Microsoft 365 環境の管理に使用する管理アカウントには、管理者特権が含まれます。 これらは、ハッカーやサイバー攻撃者にとって貴重なターゲットです。 

まず、管理用に管理者アカウントのみを使用します。 管理者は、通常の非管理用に個別のユーザー アカウントを持ち、ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。

多要素認証と条件付きアクセスで管理者アカウントを保護します。 詳細については、「管理者アカウントの [保護」を参照してください](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。 

次に、365 で特権アクセス管理Officeします。 特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。 これは、機密データへの永続的なアクセスまたは重要な構成設定へのアクセスを持つ既存の特権管理者アカウントを使用する可能性のある侵害から組織を保護するのに役立ちます。

- [特権アクセス管理の概要](privileged-access-management-overview.md)
- [特権アクセス管理を構成する](privileged-access-management-configuration.md)

もう 1 つの推奨事項は、管理作業用に特別に構成されたワークステーションを使用する方法です。 これらは、管理タスクにのみ使用される専用デバイスです。 「 [特権アクセスのセキュリティ保護」を参照してください](/windows-server/identity/securing-privileged-access/securing-privileged-access)。

最後に、テナントに 2 つ以上の緊急アクセス アカウントを作成することで、管理アクセスの不注意による影響を軽減できます。 「Azure AD で緊急 [アクセス アカウントを管理する」を参照してください](/azure/active-directory/users-groups-roles/directory-emergency-access)。 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>手順 3: 推奨される ID とデバイス アクセス ポリシーを構成する
多要素認証 (MFA) と条件付きアクセス ポリシーは、侵害されたアカウントや不正アクセスを軽減するための強力なツールです。 一緒にテストされた一連のポリシーを実装することをお勧めします。 展開手順を含む詳細については、「Identity and [device access configurations」を参照してください](../security/defender-365-security/microsoft-365-policies-configurations.md)。

 これらのポリシーは、次の機能を実装します。
- Mult-factor 認証
- 条件付きアクセス
- Intune アプリ保護 (デバイスのアプリとデータ保護)
- Intune デバイス コンプライアンス
- Azure AD Identity Protection

Intune デバイスのコンプライアンスを実装するには、デバイスの登録が必要です。 デバイスを管理すると、環境内のリソースへのアクセスを許可する前に、デバイスが正常で準拠することを確認できます。 [「Intune での管理用デバイスの登録」を参照してください。](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>手順 4: SharePoint デバイス アクセス ポリシーを構成する

Microsoft では、デバイス アクセス制御を使用して、機密性の高い規制の高いコンテンツを使用して SharePoint サイト内のコンテンツを保護することを推奨します。 詳細については [、「SharePoint サイトとファイルのセキュリティ保護に関するポリシーの推奨事項」を参照してください](../security/defender-365-security/sharepoint-file-access-policies.md)。



