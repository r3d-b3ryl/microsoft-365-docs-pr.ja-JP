---
title: Microsoft 365 の情報障壁
description: Microsoft 365 で情報障壁を構成する方法について説明します。
keywords: Microsoft 365、内部者のリスク、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613845"
---
# <a name="information-barriers-in-microsoft-365"></a>Microsoft 365 の情報障壁

Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にし、必要に応じて特定のユーザーグループ間の通信とコラボレーションを制限する方法をサポートします。 これには、組織での競合を回避するために2つのグループ間の通信とコラボレーションを制限する必要がある状況やシナリオが含まれます。 これには、内部情報を保護するために組織内の特定のユーザー間での通信とコラボレーションを制限する必要がある場合もあります。

情報バリアは、Microsoft Teams、SharePoint Online、OneDrive for business でサポートされています。 コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。 情報バリアポリシーは、次のような状況で使用できます。

- 営業担当営業グループのユーザーは、マーケティングチームとファイルを通信または共有することはできません。
- 機密企業情報を扱う財務担当者は、組織内の特定のグループとファイルを通信または共有することはできません。
- 組織内の特定のグループに属するユーザーとの通信を、取引先機密資料を含む内部チームに対して行うことはできません。
- 研究チームは、製品開発チームとの通話またはオンラインチャットのみを行います。

## <a name="configure-information-barriers-for-microsoft-365"></a>Microsoft 365 の情報障壁を構成する

組織の情報障壁を構成するには、次の手順を使用します。

![Insider リスクソリューション情報障壁の手順](../media/ir-solution-ib-steps.png)

1. Microsoft 365 の [情報障壁](information-barriers.md) について
2. [前提条件とアクセス許可を](information-barriers-policies.md#prerequisites)構成する
3. [組織内のユーザーの](information-barriers-policies.md#part-1-segment-users)セグメント化
4. [情報バリアポリシー](information-barriers-policies.md#part-2-define-information-barrier-policies)を作成および構成する
5. [情報バリアポリシー](information-barriers-policies.md#part-3-apply-information-barrier-policies)の適用

## <a name="more-information-about-information-barriers"></a>情報障壁に関する詳細情報

- [情報障壁ポリシーの属性](information-barriers-attributes.md)
- [情報バリアポリシーを編集または削除する](information-barriers-edit-segments-policies.md)