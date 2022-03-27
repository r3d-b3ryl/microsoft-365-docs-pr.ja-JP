---
title: 組織から招待できるユーザーを制限する
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
description: ゲストまたは共有チャネル参加者として招待できるユーザーを特定の組織に制限する方法について説明します。
ms.openlocfilehash: 599f83a4464498f7a964f02a955f802cb8545432
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716063"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>組織から招待できるユーザーを制限する

別の組織と共同作業を行い、Teams のゲストまたは共有チャネル メンバーとしてその組織に招待できるユーザーを制限する場合は、Azure Active Directory のテナント間アクセス設定で招待できるユーザーを指定できます。

> [!NOTE]
> テナント間のアクセス設定の変更は、有効に 2 時間かかる場合があります。

## <a name="create-a-security-group"></a>セキュリティ グループを作成する

別の組織に招待できるユーザーを指定する最も簡単な方法は、セキュリティ グループを使用する方法です。 定義済みのメンバーシップまたは動的セキュリティ グループを持つセキュリティ グループを使用できます。 既存のセキュリティ グループを使用するか、この目的のために新しいセキュリティ グループを作成できます。

セキュリティ グループを作成する
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **Active Directory] ページで** 、[グループ] **を選択し** 、[新しいグループ] **を選択します**。
1. [グループ **の種類]** で [ **セキュリティ] を選択します**。
1. グループ名 **を入力します。** 
1. 必要に応じて、グループの説明を追加します。
1. たとえば **Azure ADグループに割り当て** 可能な場合は、[いいえ] を選択 **します**。
1. 定義済みのメンバーシップの種類 **(必須) を選択します**。
1. 動的ユーザー メンバーシップを使用している場合[](/azure/active-directory/enterprise-users/groups-dynamic-membership)は、グループの所有者とメンバー、または動的クエリを追加します。
1. **[作成]** を選択します。 グループが作成され、メンバーを追加する準備が整いました。

## <a name="add-an-organization"></a>組織の追加

別の組織とのコラボレーション ルールを定義するには、その組織をテナント間アクセスAzure ADに追加する必要があります。 組織をまだ追加していない場合は、次の手順に従って組織を追加します。

組織を追加するには
1. [[Azure Active Directory](https://aad.portal.azure.com)] で [**外部 ID] を選択** し、[テナント間アクセス設定 **(プレビュー)]**.1 を選択します。 [組織 **の設定] を選択します**。
1. [組織 **の追加] を選択します**。
1. [組織 **の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果で組織を選択し、[追加] を **選択します**。
1. 組織が [組織の設定] **リストに表示** されます。 この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

## <a name="choose-who-can-be-invited-by-an-organization"></a>組織から招待できるユーザーを選択する

組織に招待できるユーザーを制限するには、次の 2 つのオプションがあります。

- ゲストとして招待できるユーザーを制限します。 これにより、ユーザーがゲストとして他の組織のAzure ADされるのを防ぐ。 これは、ファイル、フォルダー、サイト、チーム、およびグループMicrosoft 365、セキュリティ グループに参加していないユーザーとの共有を防止します。
- 外部共有チャネルに追加できるユーザーを制限します。 これにより、セキュリティ グループに所属していないユーザーが、他の組織の共有チャネルに追加されるのを防ぐ。

[[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。

ゲストとして招待できるユーザーを制限する
1. 変更する組織の送信アクセス リンクを選択します。
1. [ **B2B コラボレーション] タブで、[** 設定のカスタマイズ] **を選択します**。
1. [アクセス **の状態] で、[** アクセスを **許可する] を選択します**。
1. [ターゲット **] で**、[外部 **ユーザーとグループの選択] を選択します**。
1. ユーザーとグループを追加するリンクを選択します。
1. 使用するセキュリティ グループを検索して選択します。
1. **[選択]** を選択します。
1. [保存 **] を** 選択し、[ **送信アクセス設定] ブレードを閉** じます。


共有チャネル参加者として招待できるユーザーを制限するには
1. 変更する組織の送信アクセス リンクを選択します。
1. **[B2B 直接接続] タブで、[** 設定のカスタマイズ] **を選択します**。
1. [アクセス **の状態] で、[** アクセスを **許可する] を選択します**。
1. [ターゲット **] で**、[外部 **ユーザーとグループの選択] を選択します**。
1. ユーザーとグループを追加するリンクを選択します。
1. 使用するセキュリティ グループを検索して選択します。
1. **[選択]** を選択します。
1. [保存 **] を** 選択し、[ **送信アクセス設定] ブレードを閉** じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B ダイレクト接続のテナント間アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[ユーザーがゲスト アカウントを持つ組織を制限する](limit-organizations-where-users-have-guest-accounts.md)

[ゲスト共有を特定の組織に制限する](limit-guest-sharing-to-specific-organization.md)