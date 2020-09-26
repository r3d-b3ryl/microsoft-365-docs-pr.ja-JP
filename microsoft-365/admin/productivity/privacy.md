---
title: Microsoft プロダクティビティスコア-プライバシー
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: 生産性スコアによるプライバシーの保護
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287300"
---
# <a name="privacy-controls-for-productivity-score"></a>生産性スコアのプライバシー制御

生産性スコアは、ユーザーが Microsoft 365 を使用する方法と、それらをサポートするテクノロジエクスペリエンスについて、組織がどのように作業を遂行するかを分析するのに役立ちます。 このスコアは、組織&#39;のパフォーマンスを従業員やテクノロジの体験手段に照らして反映し、自分のスコアを自分のような組織と比較します。 詳細については、「 [生産性スコアの概要](productivity-score.md) 」のトピックをご覧ください。

お客様のプライバシーは我々にとって重要であり、Microsoft のプライバシーに関する声明は [こちらで](https://privacy.microsoft.com/privacystatement)ご覧いただけます。 生産性スコアでは、組織内のユーザーがどのように機能するかについて、重要な情報が提供されます。 そのため、弊社では、お客様の信頼を侵害せずに、意味のある方法で情報が操作可能であることを確認するための制御を提供することを目的としています。

データをより安全に処理できるように、次のコントロールを用意しています。

- 生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割。
- ユーザーレベルの指標の匿名化。
- 従業員の利便性をオプトアウトする機能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割

テナントレベルの洞察、ユーザーごとのレベルの詳細を含む、管理者の役割を使用して生産性のスコアを表示するには、役割が次のいずれかである必要があります。

- グローバル管理者
- Exchange の管理者
- SharePoint 管理者
- Skype for Business 管理者
- Teams 管理者
- グローバル閲覧者
- レポート閲覧者

変更の管理と導入を担当するが、IT 管理者ではないユーザーに対して、テナントレベルの洞察やユーザーごとの詳細情報を含む完全な機能へのアクセスを許可している場合は、それらのユーザーにレポートリーダーの役割を与えることができます。

従業員の経験の範囲内で、カテゴリ詳細ページごとにユーザーごとのレベルのアクティビティの詳細をグリッド形式で提供します。 このレベルの詳細は、生産性スコアの可能性があるすべての訪問者には適していないため、Azure AD-利用状況の概要レポート閲覧者ロールにカスタムロールを作成しました。これにより、組織内のより広範な訪問者に対して、集約された指標のみにアクセスできるようにすることができます。

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生産性レポートの [通信] ページ":::

## <a name="anonymization-of-user-level-metrics"></a>ユーザーレベルの指標の匿名化

すべてのレポートで匿名で収集されるデータを作成するには、全体管理者である必要があります。 これにより、生産性スコアや Microsoft 365 の使用状況を含む、すべてのレポートのユーザー、グループ、サイト名など、識別可能な情報が非表示になります。

1. 管理センターで、[設定] [ **Settings**   >   **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。
2. [  **レポート** ] を選択し、[  **生産性スコアと利用状況レポート] にユーザー、グループ、およびサイト名の匿名識別子を表示**するように選択します。 この設定は、利用状況レポートだけでなく、テンプレートアプリにも適用されます。
3. [  **Save changes**] を選びます。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="ユーザー情報をレポート用に匿名にします。":::

## <a name="capability-to-opt-out-of-employee-experience"></a>従業員の experience をオプトアウトする機能

また、全般的な可用性で、生産性スコアの従業員経験領域をオプトアウトする機能を提供します。 この設定をオンにすると、組織内のすべてのユーザーがこれらの指標を表示したり、カテゴリの通信、会議、チームワーク、コンテンツコラボレーション、モビリティを含むすべての計算から組織を削除したりすることができなくなります。

1. 管理センターで、[設定] [ **Settings**   >   **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。
2. [  **レポート** ] を選択し、[  **組織&#39;のデータを生産性スコアの従業員が**利用できるようにする] というボックスをオフにします。 Intune 構成マネージャーでエンドポイント分析のデータ共有設定を変更する方法について理解するには、[ **詳細情報**] をクリックします。
3. [  **Save changes**] を選びます。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="[組織の設定] ページ従業員の利便性から選択できます。":::