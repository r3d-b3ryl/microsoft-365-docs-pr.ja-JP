---
title: 組織が招待できるユーザーを制限する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: ゲストまたは共有チャネル参加者として特定の組織に招待できるユーザーを制限する方法について説明します。
ms.openlocfilehash: 599f83a4464498f7a964f02a955f802cb8545432
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716063"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>組織が招待できるユーザーを制限する

別の組織と共同作業を行い、Teamsのゲストまたは共有チャネル メンバーとしてその組織に招待できるユーザーを制限する場合は、Azure Active Directoryのテナント間アクセス設定で招待できるユーザーを指定できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

## <a name="create-a-security-group"></a>セキュリティ グループを作成する

別の組織に招待できるユーザーを指定する最も簡単な方法は、セキュリティ グループを使用することです。 定義されたメンバーシップまたは動的セキュリティ グループでセキュリティ グループを使用できます。 この目的のために、既存のセキュリティ グループを使用するか、新しいセキュリティ グループを作成できます。

セキュリティ グループを作成する
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[Active Directory**] ページで[**グループ**]、[**新しいグループ**] の順に選択します。
1. **[グループの種類**] で [**セキュリティ**] を選択します。
1. **グループ名を入力します。** 
1. 必要に応じて、グループの説明を追加します。
1. **Azure ADロールをグループに割り当てることができる場合は**、[いいえ] を選択 **します**。
1. 定義済みの **メンバーシップの種類 (必須)** を選択します。
1. 動的ユーザー メンバーシップを使用している場合は、グループの所有者とメンバー、または [動的クエリ](/azure/active-directory/enterprise-users/groups-dynamic-membership) を追加します。
1. **[作成]** を選択します。 グループが作成され、メンバーを追加する準備が整いました。

## <a name="add-an-organization"></a>組織を追加する

別の組織とのコラボレーション ルールを定義するには、その組織をAzure ADクロステナント アクセス設定に追加する必要があります。 組織をまだ追加していない場合は、この手順に従って追加します。

組織を追加する方法
1. [Azure Active Directory](https://aad.portal.azure.com)で [**外部 ID] を** 選択し、**クロステナント アクセス設定 (プレビュー)**.1 を選択します。 **[組織設定]** を選択します。
1. **[組織の追加]** を選択します。
1. **[組織の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果から組織を選択して、**[追加]** を選択します。
1. 組織が **[組織設定]** リストに表示されます。 この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

## <a name="choose-who-can-be-invited-by-an-organization"></a>組織から招待できるユーザーを選択する

組織に招待できるユーザーを制限するには、次の 2 つのオプションがあります。

- ゲストとして招待できるユーザーを制限します。 これにより、ユーザーが他の組織のAzure ADにゲストとして追加されなくなります。 これにより、ファイル、フォルダー、サイト、チーム、Microsoft 365 グループをセキュリティ グループに含まれていないユーザーと共有できなくなります。
- 外部共有チャネルに追加できるユーザーを制限します。 これにより、セキュリティ グループに所属していないユーザーが他の組織の共有チャネルに追加されるのを防ぎます。

[[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。

ゲストとして招待できるユーザーを制限するには
1. 変更する組織の送信アクセス リンクを選択します。
1. **B2B コラボレーション** タブで、[設定の **カスタマイズ**] を選択します。
1. **[アクセスの状態**] で、[**アクセスを許可する**] を選択します。
1. [ **ターゲット]** で、[ **外部ユーザーとグループの選択] を選択します**。
1. ユーザーとグループを追加するリンクを選択します。
1. 使用するセキュリティ グループを検索して選択します。
1. **[選択]** を選択します。
1. **[保存]** を選択し、**[送信アクセス設定]** ブレードを閉じます。


共有チャネル参加者として招待できるユーザーを制限するには
1. 変更する組織の送信アクセス リンクを選択します。
1. **[B2B 直接接続]** タブで、**[設定のカスタマイズ]** を選択します。
1. **[アクセスの状態**] で、[**アクセスを許可する**] を選択します。
1. [ **ターゲット]** で、[ **外部ユーザーとグループの選択] を選択します**。
1. ユーザーとグループを追加するリンクを選択します。
1. 使用するセキュリティ グループを検索して選択します。
1. **[選択]** を選択します。
1. **[保存]** を選択し、**[送信アクセス設定]** ブレードを閉じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 直接接続のクロス テナント アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[ユーザーがゲスト アカウントを持つ組織を制限する](limit-organizations-where-users-have-guest-accounts.md)

[ゲスト共有を特定の組織に制限する](limit-guest-sharing-to-specific-organization.md)