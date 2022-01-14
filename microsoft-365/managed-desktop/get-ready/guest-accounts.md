---
title: ゲスト アカウントの前提条件
description: ゲスト アカウントの構成ガイドラインと調整方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 64b0acabf76e1ceb12bd056b02cb2b949df9c957
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035042"
---
# <a name="prerequisites-for-guest-accounts"></a>ゲスト アカウントの前提条件

## <a name="external-collaboration-settings"></a>外部コラボレーションの設定

Microsoft Managed Desktop では、ゲスト アカウント アクセス用に組織でAzure AD構成をお勧めします。 これらの設定は [、Azure portal](https://portal.azure.com) の [外部 **ID/ 外部コラボレーション設定] で調整できます**。

-   ゲスト **ユーザー アクセスの場合**、ゲスト ユーザーに設定すると、ディレクトリ オブジェクトのプロパティ **とメンバーシップへのアクセスが制限されています**
-   [ **ゲスト招待の設定**] で、[メンバー ユーザー] に設定し、特定の管理者ロールに割り当てられたユーザーは、メンバーのアクセス許可を持つゲストを含むゲスト **ユーザーを招待できます。**

Microsoft Managed Desktop では、ゲスト アカウント アクセス用に組織Azure AD構成が必要です。 この設定は [、Azure portal](https://portal.azure.com) の [外部 **ID/ 外部コラボレーション設定] で調整できます**。

-   **[コラボレーションの制限]** で、次のオプションを選択します。
    -   [任意の **ドメインへの招待の** 送信を許可する ( 最も包括的な) ] を選択した場合、他の構成は必要ありません。
    -   [指定した **ドメインへの** 招待を拒否する] を選択した場合は、Microsoft.com ドメインに一覧が表示されません。
    -   [指定した **ドメインへの** 招待のみを許可する ] (最も制限の厳しい) を *選択した場合* は、Microsoft.com がターゲット ドメインに表示されます。

これらの設定を操作する制限を設定する場合は、必ずモダン Workplace サービス Azure Active Directory **を除外してください**。 たとえば、ゲスト アカウントによる Intune ポータルへのアクセスを妨げる条件付きアクセス ポリシーがある場合は、このポリシーからモダン **Workplace サービス** アカウント グループを除外します。

詳細については [、「B2B 外部コラボレーションを有効にする」および「ゲストを招待できるユーザーを管理する」を参照してください](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)。

## <a name="unlicensed-intune-admin"></a>ライセンスのない Intune 管理者

[ **ライセンスのない管理者へのアクセスを許可する** ] 設定を有効にする必要があります。 この設定を有効にしない場合、サービスを提供する組織にアクセスしようとAzure ADが発生する可能性があります。 アクセス範囲は、運用スタッフを含むユーザーに割り当てられた役割によって定義されますので、セキュリティへの影響を気にすることなく、この設定を安全に有効にできます。

この設定を有効にするには、次の手順を実行します。

1. 管理センターのMicrosoft エンドポイント マネージャー[移動します](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. [テナント管理 **の役割**  >  **]**  >  **[管理者ライセンス] に移動します**。
3. [ **ライセンスのない管理者へのアクセスを許可する] で、[** はい] を **選択します**。

> [!IMPORTANT]
> [はい] を選択した後は、この設定を元に **戻すことはできません**。

詳細については、「ライセンスのない管理者」[を参照Microsoft Intune。](/mem/intune/fundamentals/unlicensed-admins)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. ゲスト アカウントの前提条件を確認します (この記事)。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
