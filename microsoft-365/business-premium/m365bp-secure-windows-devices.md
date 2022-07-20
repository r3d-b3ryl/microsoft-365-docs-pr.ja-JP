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
ms.date: 07/19/2022
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: 職場または学校アカウントへのサインイン時に Windows デバイスが受け取る既定のデバイス ポリシーの設定の構成について説明します。
ms.openlocfilehash: f497dab832b9980225be2e689d2c980860a01454
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894879"
---
# <a name="secure-windows-devices"></a>Windows 10 デバイスをセキュリティで保護する

ここでの目的は、Windows 10 または 11 の既定のデバイス ポリシーの一部である設定を構成することです。職場アカウントでサインインして、モバイル デバイスや PC などの Windows デバイスに接続するすべてのユーザーは、これらの設定を自動的に受け取ります。セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Business Premium のユーザー用に Windows デバイスを設定する前に、すべての Windows デバイスで Windows 10 Pro が実行されていることを確認してください。

Windows 10 Pro は、Windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro および Windows 11 Pro を補完し、Microsoft 365 Business Premium の一元管理とセキュリティ制御を有効にする一連のクラウド サービスとデバイス管理機能です。

[Microsoft 365 Business Premium の要件について詳しく説明します](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab)。

## <a name="windows-10-pro"></a>Windows 10 Pro

Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro などの以前のバージョンの Windows デバイスを実行している場合、Microsoft 365 Business Premium サブスクリプションでは、これらのデバイスを Windows 10 Pro または Windows 11 Pro にアップグレードできます。
  
Windows デバイスをアップグレードする方法の詳細については、[「Windows デバイスを Windows 10 Pro にアップグレードする」](m365bp-upgrade-windows-10-pro.md)を参照してください。

## <a name="secure-your-windows-10-and-11-devices"></a>Windows 10 と 11 のデバイスをセキュリティで保護する

既定では、すべての設定が **オン** になっています。次の設定を使用できます。<br/><br/>

|Setting  <br/> |説明  <br/> |
|:-----|:-----|
|Microsoft Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  <br/> |インターネットに接続されている危険から PC を保護するには、Microsoft Defender ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で PC を Web ベースの脅威から保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)」を参照してください。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |

## <a name="next-objective"></a>次の目標

[Windows デバイスを管理する](m365bp-manage-windows-devices.md)
