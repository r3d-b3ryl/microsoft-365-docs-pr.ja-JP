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
ms.openlocfilehash: 469edf3e8ae856ea6e94bada8ffb9d6c97ba8b66
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634473"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software)[は、リアルタイム](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0)のコラボレーションとコミュニケーション、会議、ファイルとアプリの共有のためのワークスペースも提供するメッセージング アプリです。

## <a name="initial-deployment"></a>初期展開

ほとんどのハードウェア ベンダーは、画像の一部としてTeamsをまだ含めません。 Microsoft Managed Desktopを使用Teamsデバイスにデバイスを展開Microsoft Intune。 すべての管理対象デバイスには、Teams .msi[パッケージがインストール](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works)されています。 この.msiを使用すると、デバイスにサインインしているすべてのユーザーがMicrosoft Teams準備が整います。 パッケージの最初のインストールが完了すると、Teams自動的に起動し、デスクトップにショートカットが追加されます。

### <a name="microsoft-intune-changes"></a>Microsoft Intune変更

Microsoft Managed DesktopテナントMicrosoft Teamsを追加します。モダン ワークプレース - Teams Machine Wide Installer x64  

## <a name="updates"></a>更新プログラム

Teamsから別の更新パスに従Microsoft 365 Apps for enterprise。 デスクトップ クライアントは自動的に更新されます。 Teams、数時間ごとに更新プログラムを確認し、ダウンロードし、コンピューターがアイドル状態になるのを待機してから、更新プログラムをサイレント インストールします。  

このTeamsグループでは、管理者は更新プログラムを制御できないので、Microsoft Managed Desktop自動更新チャネル[を使用します](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手動で更新Teams

個々のユーザーは更新プログラムをダウンロードできます。 アプリの上部にある [プロファイル] ドロップダウンで、[更新プログラムの確認 **] を選択します**。 更新プログラムが入手可能であれば、ダウンロードが実行されて、コンピューターがアイドル状態のときにサイレント インストールされます。

## <a name="delivery-optimization-of-updates"></a>更新プログラムの配信の最適化

既定では、Teams配信の最適化が有効になっているので、管理者やユーザーからのアクションは必要とされません。
