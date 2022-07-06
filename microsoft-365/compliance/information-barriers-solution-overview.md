---
title: 情報バリア
description: Microsoft Purview で情報バリアを構成する方法について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: 21ad4f0cc6614bed3c579a8025d83200446fec18
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627241"
---
# <a name="information-barriers"></a>情報バリア

Microsoft 365 では、グループや組織間のコミュニケーションとコラボレーションが可能になり、必要に応じて特定のユーザー グループ間の通信とコラボレーションを制限する方法がサポートされます。 これには、2 つのグループ間の通信とコラボレーションを制限して、組織で競合が発生しないようにする状況やシナリオが含まれる場合があります。 これには、内部情報を保護するために組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限する必要がある状況も含まれる場合があります。

Microsoft Purview Information Barriers (IB) は、Microsoft Teams、SharePoint Online、およびOneDrive for Businessでサポートされています。 コンプライアンス管理者または IB 管理者は、Microsoft Teams のユーザー グループ間の通信を許可または禁止するポリシーを定義できます。 IB ポリシーは、次のような状況で使用できます。

- その日のトレーダー グループのユーザーは、マーケティング チームとファイルを通信したり共有したりしないでください
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしないでください
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしないでください。
- リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります

## <a name="configure-information-barriers"></a>情報バリアを構成する

組織の IB を構成するには、次の手順に従います。

![インサイダー リスク ソリューション情報バリアの手順。](../media/ir-solution-ib-steps.png)

1. [情報バリア](information-barriers.md)について学習する
2. [前提条件とアクセス許可を構成する](information-barriers-policies.md#step-1-make-sure-prerequisites-are-met)
3. [組織内のユーザーをセグメント化する](information-barriers-policies.md#step-2-segment-users-in-your-organization)
4. [IB ポリシー](information-barriers-policies.md#step-3-create-ib-policies)を作成して構成する
5. [IB ポリシーを適用する](information-barriers-policies.md#step-4-apply-ib-policies)

## <a name="more-information-about-information-barriers"></a>情報バリアの詳細

- [IB ポリシーの属性](information-barriers-attributes.md)
- [IB ポリシーを編集または削除する](information-barriers-edit-segments-policies.md)
