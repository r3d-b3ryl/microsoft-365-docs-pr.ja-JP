---
title: 情報バリア
description: Microsoft Purviewで情報バリアを構成する方法について説明します。
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
ms.openlocfilehash: aaba1c642d4615d3eb5163736450f3f8f3c27062
ms.sourcegitcommit: 99494a5530ad64802f341573ad42796134190296
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2022
ms.locfileid: "65396181"
---
# <a name="information-barriers"></a>情報バリア

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft 365は、グループや組織間のコミュニケーションとコラボレーションを可能にし、必要に応じて特定のユーザー グループ間のコミュニケーションとコラボレーションを制限する方法をサポートします。 これには、2 つのグループ間の通信とコラボレーションを制限して、組織で競合が発生しないようにする状況やシナリオが含まれる場合があります。 これには、内部情報を保護するために組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限する必要がある状況も含まれる場合があります。

Microsoft Purview Information Barriers (IB) は、Microsoft Teams、SharePoint Online、およびOneDrive for Businessでサポートされています。 コンプライアンス管理者または IB 管理者は、Microsoft Teams内のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。 IB ポリシーは、次のような状況で使用できます。

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
