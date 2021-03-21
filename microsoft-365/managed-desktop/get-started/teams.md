---
title: Microsoft Teams
description: Teams がデバイスにインストールされ、その後更新される方法
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920658"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) は組織 [のメッセージング](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) アプリであり、リアルタイムのコラボレーションとコミュニケーション、会議、ファイルとアプリの共有のためのワークスペースも提供します。

## <a name="initial-deployment"></a>初期展開

ほとんどのハードウェア ベンダーは、イメージの一部として Teams をまだ含めないので、Microsoft Managed Desktop は Microsoft Intune を使用して Teams をデバイスに展開します。 すべての管理対象デバイスに [Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) パッケージがインストールされ、デバイスにサインインしているすべてのユーザーが Microsoft Teams を使用できる状態にできます。 パッケージのインストールが最初に完了すると、Teams は自動的に起動し、デスクトップにショートカットを追加します。

### <a name="microsoft-intune-changes"></a>Microsoft Intune の変更点

Microsoft Managed Desktop は、Microsoft Teams の Azure ADに 2 つのアプリケーションを追加します。 デバイスに応じて、64 ビットまたは 32 ビットのクライアントに展開されます。  

- モダン ワークプレース – Teams Machine Wide Installer x64  
- モダン ワークプレース – Teams Machine Wide Installer x32

## <a name="updates"></a>更新プログラム

Teams は、Microsoft 365 Apps for enterprise とは別の更新パスに従い、デスクトップ クライアントは自動的に更新します。 Teams は数時間ごとに更新プログラムをチェックし、ダウンロードし、コンピューターがアイドル状態になるのを待って、更新プログラムをサイレント インストールします。  

Teams 製品グループでは、管理者が更新プログラムを制御できないので、Microsoft Managed Desktop は標準の自動更新チャネル [を使用します](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>Teams を手動で更新する

個々のユーザーは、アプリの右上部にある [プロファイル] ドロップダウン メニューで [更新プログラムの確認] を選択して更新    ****   プログラムをダウンロードすることもできます。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態のときにダウンロードされ、サイレント インストールされます。

## <a name="delivery-optimization-of-updates"></a>更新プログラムの配信の最適化

Teams 更新プログラムの配信の最適化は既定で有効になっています。管理者またはユーザーからのアクションは必要とされません。