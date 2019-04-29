---
title: '手順 6: 管理を容易にするためのグループの使用'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD のセルフ サービスによるグループ管理について理解し、構成します。
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283527"
---
# <a name="step-6-use-groups-for-easier-management"></a>手順 6: 管理を容易にするためのグループの使用

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>ユーザーが各自のグループを作成および管理できるようにする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、IT 管理者ではなくグループの所有者が管理できる Azure Active Directory (Azure AD) グループを指定します。 *セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。 

ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。

>[!Note]
>セルフサービスによるグループ管理は Azure AD セキュリティと Office 365 グループに対してのみ使用できます。 メールが有効なグループ、配布リスト、またはオンプレミスの Active Directory ドメイン サービス (AD DS) から同期されたことがあるグループではできません。
>

詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-self-service-groups)を確認できます。

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>動的グループ メンバーシップをセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、ユーザー アカウントを Azure AD グループのメンバーとして自動的に追加または削除するための一連のルールを作成します。 これは*動的グループ メンバーシップ*と呼ばれます。 ルールはユーザー アカウントの属性 (部門や国など) に基づいています。

ルールの適用方法を次に説明します。

- 新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。
- ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのグループのメンバーになります。
- ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。
- ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。

動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。

「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。

このセクションの手順を実行すると次のような結果が得られます。

- 動的メンバーシップを構成できる Azure AD グループのセット
- 各動的グループのルール セット

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-dyn-groups)を確認できます。

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>自動ライセンスをセットアップする

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

このセクションでは、一連のサブスクリプションのライセンスをグループのすべてのメンバーに自動的に割り当てるため、Azure AD でセキュリティ グループを構成します。 これは*グループベースのライセンス*と呼ばれます。 グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。

Microsoft 365 Enterprise では、次の両方のライセンスを割り当てる Azure AD セキュリティ グループを構成します。

- Office 365 Enterprise E3 または E5
- Enterprise Mobility + Security (EMS) E3 または E5

手順 2 で指定したグループを使用して、グループ内のすべてのユーザーに Office 365 と EMS の両方のライセンスが割り当てられている必要があるアカウントのリストが含まれているグループを検索します。すべてのグループ メンバーに割り当てることができる十分な数のライセンスがあることを確認します。ライセンスが不足すると、ライセンスが使用可能になるまで、新しいユーザーにライセンスが割り当てらません。

>[!Note]
>Azure B2B (企業間) アカウントが含まれているグループに対しては*グループベースのライセンス*を構成しないでください。
>

「[Azure Active Directory のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」にある追加情報を参照してください。

「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」を参照してください。

このセクションの手順を実行すると次のような結果が得られます。

- グループベースのライセンスに適したセキュリティ グループを特定している。
- グループベースのライセンスに対応してこれらのグループを構成している。

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-group-license)を確認できます。

## <a name="next-step"></a>次の手順

[ID インフラストラクチャの終了条件](identity-exit-criteria.md)
