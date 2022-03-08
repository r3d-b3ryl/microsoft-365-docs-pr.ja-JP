---
title: セキュリティで保護Windowsデバイス
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 仕事または学校のアカウントにサインインすると、Windowsデバイスが受け取る既定のデバイス ポリシーの設定を構成する方法について説明します。
ms.openlocfilehash: b58e63abf19c3078eb5d4356b155df13804c95d5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330946"
---
# <a name="secure-windows-devices"></a>セキュリティで保護Windowsデバイス

この記事は、ユーザーにMicrosoft 365 Business Premium。

ここで構成する設定は、ユーザーまたは 11 の既定のデバイス Windows 10の一部です。 モバイル デバイスや PC など、Windowsを自分の仕事用アカウントでサインインして接続するユーザーは、自動的にこれらの設定を受け取る。 セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。
  
## <a name="settings-to-secure-windows-10-devices"></a>Windows 10 デバイスをセキュリティで保護する設定

既定では、すべての設定が **オン** になっています。次の設定を使用できます。<br/><br/>

|Setting  <br/> |説明  <br/> |
|:-----|:-----|
|Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  <br/> |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で PC を Web ベースの脅威から保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化してデータを保護し、コンピューターが紛失または盗まれた場合のデータの露出を保護します。 詳細については、「 [BitLocker FAQ」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |
