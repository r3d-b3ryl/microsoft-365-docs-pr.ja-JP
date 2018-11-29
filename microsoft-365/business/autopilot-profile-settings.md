---
title: AutoPilot プロファイルの設定について
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動操縦装置のプロファイルを使用して、ユーザーのデバイス上の Windows のインストール方法を制御できます。プロファイルには、既定値が含まれているし、オプションの設定は、Cortana のインストールをスキップするように。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869025"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

Windows の自動操縦装置のプロファイルを使用してユーザー デバイス上インストール取得方法を制御できます。プロファイルには、次の設定が含まれています。
  
 **自動操縦既定の機能 (必須) に自動的に設定されています。**
  
|**設定**|**説明**|
|:-----|:-----|
|Cortana、OneDrive、OEM の登録のスキップ  <br/> |Cortana および個人の OneDrive のようなコンシューマー アプリケーションのインストールをスキップします。デバイス ユーザーは、彼または彼女は、デバイス上のローカル管理者として、後でインストールできます。元の製造元の登録は、マイクロソフトの 365 のビジネスが、デバイスを管理するためにスキップされます。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社は、 [Office 365 のサインイン ページを追加、会社のブランド](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)には、デバイスのユーザーは、サインイン時に、その経験を取得します。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー ID は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business 資格情報を使って Windows と Office 365 にサインインします。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。  <br/> |
   
