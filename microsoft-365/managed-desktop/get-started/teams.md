---
title: Microsoft Teams
description: Teams をデバイスにインストールし、後で更新する方法
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950941"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) は、組織の [メッセージングアプリ](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) であり、リアルタイムのコラボレーション、コミュニケーション、会議、およびファイルとアプリの共有のためのワークスペースも提供します。

## <a name="initial-deployment"></a>初期展開

ほとんどのハードウェアベンダーには、Teams が画像の一部として含まれていないため、Microsoft Managed Desktop は Microsoft Intune を使用してチームをデバイスに展開します。 すべての管理対象デバイスに [Teams .msi パッケージ](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) がインストールされており、デバイスにサインインするすべてのユーザーが Microsoft teams を使用する準備が整っていることを確認します。 最初にパッケージがインストールを終了すると、Teams が自動的に起動し、デスクトップへのショートカットが追加されます。

### <a name="microsoft-intune-changes"></a>Microsoft Intune の変更

Microsoft マネージドデスクトップでは、Microsoft Teams 用の Azure AD 組織に2つのアプリケーションが追加されています。 デバイスに応じて、次のように64ビットまたは32ビットのどちらかのクライアントに展開されます。  

- モダンワークプレース: Teams Pc Wide Installer x64  
- モダンワークプレース-Teams コンピューター全体のインストーラー x32

## <a name="updates"></a>更新プログラム

Teams は、Microsoft 365 Apps for enterprise とデスクトップクライアントを自動的に更新する別の更新パスに従います。 Teams は数時間ごとに更新をチェックし、それらをダウンロードして、コンピューターがアイドル状態になってから更新プログラムをサイレントインストールするまで待機します。  

Teams 製品グループでは、管理者が更新プログラムを制御することを許可していないため、Microsoft Managed Desktop は [標準の自動更新チャネル](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)を使用します。

### <a name="manually-updating-teams"></a>Teams を手動で更新する

各ユーザーは**Check for updates**   、 **Profile**   アプリの右上にある [プロファイル] ドロップダウンメニューで [更新プログラムの確認] を選択して更新プログラムをダウンロードすることもできます。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、サイレントにインストールされます。

## <a name="delivery-optimization-of-updates"></a>更新プログラムの配信の最適化

Teams の更新の配信の最適化は既定で有効になっており、管理者またはユーザーからのアクションは必要ありません。 