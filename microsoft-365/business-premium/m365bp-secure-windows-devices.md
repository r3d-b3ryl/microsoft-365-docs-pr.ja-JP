---
title: Windows 10 デバイスをセキュリティで保護する
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
ms.localizationpriority: high
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
description: 職場または学校アカウントへのサインイン時に Windows デバイスが受け取る既定のデバイス ポリシーの設定の構成について説明します。
ms.openlocfilehash: d8a32dd5378ed1b16e6126e9091f2bd2bb8515f5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65094640"
---
# <a name="secure-windows-devices"></a>Windows 10 デバイスをセキュリティで保護する

この記事は Microsoft 365 Business Premium に適用されます。

ここで構成する設定は、Windows 10 または 11 の既定のデバイス ポリシーの一部です。職場アカウントでサインインして、モバイル デバイスや PC などの Windows デバイスに接続するすべてのユーザーは、これらの設定を自動的に受け取ります。セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。
  
## <a name="settings-to-secure-windows-10-devices"></a>Windows 10 デバイスをセキュリティで保護する設定

既定では、すべての設定が **オン** になっています。次の設定を使用できます。<br/><br/>

|Setting  <br/> |説明  <br/> |
|:-----|:-----|
|Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  <br/> |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で PC を Web ベースの脅威から保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)」を参照してください。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |
