---
title: Microsoft Teams
description: デバイスTeamsインストールされ、その後更新される方法
keywords: Microsoft Managed Desktop、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: ITPro
ms.openlocfilehash: 21d69770fb16ac40b25cd9ff4fefd5ccf5b2f0fb
ms.sourcegitcommit: babc2dad1c0e08a9237dbe4956ffd21c0214db83
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62345941"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software)[は、リアルタイム](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0)のコラボレーションとコミュニケーション、会議、ファイルとアプリの共有のためのワークスペースも提供するメッセージング アプリです。

## <a name="initial-deployment"></a>初期展開

ほとんどのハードウェア ベンダーは、画像の一部としてTeamsをまだ含めません。 Microsoft Managed Desktop は、Teamsを使用してデバイスにMicrosoft Intune。 すべての管理対象デバイスには、Teams .msi[パッケージがインストール](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works)されています。 この.msiを使用すると、デバイスにサインインしているすべてのユーザーが、Microsoft Teams準備ができていることを確認します。 パッケージの最初のインストールが完了すると、Teams自動的に開始され、デスクトップにショートカットが追加されます。

### <a name="microsoft-intune-changes"></a>Microsoft Intune変更

Microsoft Managed Desktop は、ユーザーの組織に 2 つのアプリケーションAzure AD追加して、Microsoft Teams。 デバイスに応じて、64 ビットまたは 32 ビットのクライアントに展開されます。  

- モダン ワークプレース – Teams ワイド インストーラー x64  
- モダン ワークプレース – Teams全体インストーラー x32

## <a name="updates"></a>更新プログラム

Teamsから別の更新パスに従Microsoft 365 Apps for enterprise。 デスクトップ クライアントは自動的に更新されます。 Teams、数時間ごとに更新プログラムをチェックし、ダウンロードし、コンピューターがアイドル状態になるのを待機してから、更新プログラムをサイレント インストールします。  

製品グループTeams管理者は更新プログラムを制御できないので、Microsoft Managed Desktop は標準の自動更新チャネル[を使用します](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手動で更新Teams

個々のユーザーは更新プログラムをダウンロードできます。 アプリの上部にある [プロファイル] ドロップダウンで、[更新プログラムの確認 **] を選択します**。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態のときにダウンロードされ、サイレント インストールされます。

## <a name="delivery-optimization-of-updates"></a>更新プログラムの配信の最適化

既定では、Teams配信の最適化が有効になっているので、管理者やユーザーからのアクションは必要とされません。
