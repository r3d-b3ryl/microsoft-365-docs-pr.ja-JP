---
title: Microsoft Teams の既定の DLP ポリシーについて説明します (プレビュー)
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
description: Microsoft Teams の既定のデータ損失防止ポリシーについて説明します
ms.openlocfilehash: 5c3a5a116da90a41abcc459808e83176dc750fe1
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624225"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)

[Microsoft Purview データ損失防止](dlp-learn-about-dlp.md)機能が拡張され、Microsoft Teams チャットとチャネル メッセージ (プライベート チャネル メッセージを含む) が追加されました。 このリリースの一環として、Microsoft Teams の既定の DLP ポリシーを作成し、初めて<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">顧客をMicrosoft Purview コンプライアンス ポータル</a>に提供しました。

## <a name="licensing"></a>ライセンス

Microsoft Teams の DLP の完全なライセンス情報については、「[Information Protection: Teams のデータ損失防止」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-teams)。

## <a name="what-does-the-default-policy-do"></a>既定のポリシーでは何が行われますか?

Teams の既定の DLP ポリシーは、組織に対して内部および外部で共有されているすべてのクレジット カード番号を追跡します。 このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。 エンド ユーザーに対するポリシー ヒントは生成されませんが、アラート イベントが生成され、管理者への重大度の低い電子メールもトリガーされます (ポリシーに追加)。 管理者は、コンプライアンス センターにログインすることで、アクティビティを表示し、ポリシーの詳細を編集できます。

管理者は、[Microsoft Purview コンプライアンス ポータル >](https://compliance.microsoft.com/compliancesettings)データ損失防止ポリシー ページでこのポリシーを表示できます。


> [!div class="mx-imgBorder"]
> ![既定の Teams DLP ポリシー。](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>既定のポリシーを編集または削除する

[既定のポリシーを編集してパフォーマンスを向上させたり、削除したり](create-test-tune-dlp-policy.md#tune-a-dlp-policy)するには、**DLP コンプライアンス管理** のアクセス許可を持つアカウントを使用するだけです。 詳細については、「 [アクセス許可」を参照してください](create-test-tune-dlp-policy.md#permissions)。

