---
title: Microsoft Teams
description: デバイスTeamsインストールされ、その後更新される方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 71fa0c380dd6e7d5d348cffb4f1113032b3ee27bdf8711191b3d12903e6b1789
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53890937"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software)は、リアルタイムの[](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0)コラボレーションとコミュニケーション、会議、ファイルとアプリの共有のためのワークスペースも提供する組織向けメッセージング アプリです。

## <a name="initial-deployment"></a>初期展開

ほとんどのハードウェア ベンダーは、イメージの一部として Teams をまだ含めないので、Microsoft マネージド デスクトップ Teams を使用してデバイスにMicrosoft Intune。 すべての管理対象デバイスには、Teams .msi[](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works)パッケージがインストールされ、デバイスにサインインしているすべてのユーザーがMicrosoft Teams準備ができていることを確認します。 パッケージの最初のインストールが完了すると、Teams自動的に開始され、デスクトップにショートカットが追加されます。

### <a name="microsoft-intune-changes"></a>Microsoft Intune変更

Microsoft マネージド デスクトップ 2 つのアプリケーションを Azure AD組織に追加Microsoft Teams。 デバイスに応じて、64 ビットまたは 32 ビットのクライアントに展開されます。  

- モダン ワークプレース – Teams ワイド インストーラー x64  
- モダン ワークプレース – Teams全体インストーラー x32

## <a name="updates"></a>更新プログラム

Teamsから別の更新パスに従いMicrosoft 365 Apps for enterpriseデスクトップ クライアントは自動的に更新します。 Teams、数時間ごとに更新プログラムをチェックし、ダウンロードし、コンピューターがアイドル状態になるのを待機してから、更新プログラムをサイレント インストールします。  

製品グループTeams管理者は更新プログラムを制御できないので、Microsoft マネージド デスクトップ更新プログラム の標準チャネル[を使用します](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手動で更新Teams

個々のユーザーは、アプリの右上部にある [プロファイル] ドロップダウン メニューで [更新プログラムの確認] を選択して更新    ****   プログラムをダウンロードすることもできます。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態のときにダウンロードされ、サイレント インストールされます。

## <a name="delivery-optimization-of-updates"></a>更新プログラムの配信の最適化

既定では、Teams配信の最適化が有効になっているので、管理者やユーザーからのアクションは必要とされません。