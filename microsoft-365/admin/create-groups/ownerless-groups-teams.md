---
title: 所有者のないMicrosoft 365 グループとチームを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
description: 所有者のないMicrosoft 365 グループまたはMicrosoft Teamsのチームの所有者になるようにメンバーを自動的に招待する方法について説明します。
ms.openlocfilehash: d578e6825ea65177138594034807244afac176c7
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64836447"
---
# <a name="manage-ownerless-microsoft-365-groups-and-teams"></a>所有者のないMicrosoft 365 グループとチームを管理する

Microsoft TeamsまたはMicrosoft 365 グループのチームは、Microsoft 365で所有者のアカウントが削除または無効になっている場合、所有者を失う可能性があります。 グループとチームでは、所有者がメンバーを追加または削除し、グループ設定を変更する必要があります。

最もアクティブなメンバーまたは所有者のないグループまたはチームが所有権を受け入れるかどうかを自動的に求めるポリシーを作成できます。 メンバーが所有者への招待を受け入れると、アクションはコンプライアンス センターの監査ログに記録されます。 ゲストは所有者として招待されることはありません。

ポリシーを作成するときに、次の項目を指定できます。
- セキュリティ グループを指定して、所有者として招待できるユーザーを制限する場合
- 通知の送信者アドレス
- 通知が送信される週数
- ポリシーの一部であるグループまたはチーム

所有者のないグループまたはチーム ポリシーを設定するには

1. 管理センターで、[**すべての** \> **設定** \> **組織の設定** を表示する] に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">、[**サービス**] タブ</a>で **[Microsoft 365 グループ**] を選択します。

1. [ **所有者がいない場合は、電子メールを送信し、アクティブなグループ メンバーに所有者になるように依頼** する] チェック ボックスをオンにします。

1. 既定の構成設定を保持する場合は、[ **保存]** を選択し、それ以外の場合 **は [ポリシーの構成** ] を選択し、次の手順を実行します。

1. [ *毎週の通知オプション* ] ページで、所有権通知を受け取ることができるユーザーを指定します。 特定のメンバーを許可またはブロックする場合は、使用するセキュリティ グループを検索して追加します。

1. 通知するアクティブなメンバーの数を入力し、通知を送信する週数を選択します。 (通知リストは最初の通知の間に作成され、変更されません)。 **[次へ**] を選択します。

1. *Whoこの電子メールが [差出人*] ページで、メールの送信者を選択し、[**次へ**] を選択します。

1. [ *件名とメッセージ* ] ページで、電子メールをカスタマイズし、必要に応じて **ポリシー ガイドラインの URL を** 含め、[ **次へ**] を選択します。

1. [ *対象となるグループの選択]* ページで、[ **特定のグループ** ] を選択し、このポリシーに含めるグループとチームを選択するか、[ **すべてのグループ**] を選択します。

1. **[次へ]** を選択します。

1. [ *校閲と終了* ] ページで設定を確認し、[ **完了]** をクリックして、[完了] を選択 **します**。

通知は、ポリシーの作成から 24 時間以内に毎週送信されます。