---
title: Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: データ損失防止の既定のポリシーについて詳しくは、Microsoft Teams
ms.openlocfilehash: 61443cdfdc116e9c25d9dad24c968876ae5d0349
ms.sourcegitcommit: db2ed146b46ade9ea62eed9cb8efff5fea7a35e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2022
ms.locfileid: "64481366"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)

[データ損失防止機能](dlp-learn-about-dlp.md)は、プライベート チャネル メッセージを含むMicrosoft Teamsチャネル メッセージを含む拡張されました。 このリリースの一環として、初めてのユーザーに対して、Microsoft Teamsの DLP <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">ポリシーを作成</a>Microsoft 365 コンプライアンス センター。

## <a name="licensing"></a>ライセンス

DLP の完全なライセンス情報については、「Microsoft Teams情報保護: データ損失防止[」を参照](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-teams)Teams。

## <a name="what-does-the-default-policy-do"></a>既定のポリシーは何をしますか?

既定の DLP ポリシーは、Teams外部で共有されるクレジット カード番号を追跡します。 このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。 エンド ユーザーのポリシー ヒントは生成されませんが、Alert イベントを生成し、管理者 (ポリシーに追加) への重大度の低い電子メールもトリガーします。 管理者は、コンプライアンス センターにログインして、アクティビティを表示し、ポリシーの詳細を編集できます。

管理者は、コンプライアンス センターの [データ損失防止ポリシー [] ページ>](https://compliance.microsoft.com/compliancesettings) ポリシーを表示できます。


> [!div class="mx-imgBorder"]
> ![DLP ポリシー Teams既定の値を使用します。](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>既定のポリシーを編集または削除する

パフォーマンス [を向上するために既定のポリシーを](create-test-tune-dlp-policy.md#tune-a-dlp-policy)編集したり、削除したりするには、DLP コンプライアンス管理アクセス許可を持つ **アカウントを** 使用します。 詳細については、「アクセス許可」 [を参照してください](create-test-tune-dlp-policy.md#permissions)。

