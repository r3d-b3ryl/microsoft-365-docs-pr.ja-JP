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
ms.date: 08/16/2022
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: 組み込みの設定を使用して会社の Windows デバイスをセキュリティで保護する方法について説明します。
ms.openlocfilehash: 76f7321f916c6c65c01906d1c1ad69e559b3c084
ms.sourcegitcommit: 9a7e853bb2f9d0ea377961d854d36b644799e5f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2022
ms.locfileid: "67364526"
---
# <a name="secure-windows-devices"></a>Windows 10 デバイスをセキュリティで保護する

ここでの目的は、Windows 10 または 11 の既定のデバイス ポリシーの一部である設定を構成することです。 モバイル デバイスやコンピューターを含む Windows デバイスを自分の職場アカウントでサインインして接続するすべてのユーザーは、これらの設定を自動的に受け取ります。 セットアップ時は既定のポリシーを受け入れて、ユーザーの特定のグループを対象にするポリシーは後で追加することをお勧めします。

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Business Premium のユーザー用に Windows デバイスを設定する前に、すべての Windows デバイスで Windows 10 Pro が実行されていることを確認してください。

Windows 10 Pro は、Windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro および Windows 11 Pro を補完し、Microsoft 365 Business Premium の一元管理とセキュリティ制御を有効にする一連のクラウド サービスとデバイス管理機能です。

[Microsoft 365 Business Premium の要件について詳しく説明します](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab)。

## <a name="windows-10-pro"></a>Windows 10 Pro

Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro などの以前のバージョンの Windows デバイスを実行している場合、Microsoft 365 Business Premium サブスクリプションでは、これらのデバイスを Windows 10 Pro または Windows 11 Pro にアップグレードできます。
  
Windows デバイスをアップグレードする方法の詳細については、[「Windows デバイスを Windows 10 Pro にアップグレードする」](m365bp-upgrade-windows-10-pro.md)を参照してください。

## <a name="secure-your-windows-10-and-11-devices"></a>Windows 10 と 11 のデバイスをセキュリティで保護する

既定では、すべての設定が **オン** になっています。次の設定を使用できます。

|Setting |説明 |
|:-----|:-----|
|Microsoft Defender ウイルス対策を使用して、コンピューターをウイルスやその他の脅威から保護するのに役立ちます  |インターネットに接続される危険性からコンピューターを保護するには、Microsoft Defender ウイルス対策を有効にする必要があります。   |
|Microsoft Edge の Web ベースの脅威からコンピューターを保護する   |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  |
|BitLocker による不正アクセスからコンピューター上のファイルとフォルダーを保護する  |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)」を参照してください。    |
|この時間アイドル状態になったときにデバイスの画面をオフにする  |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  |

## <a name="next-objective"></a>次の目標

[Windows デバイスを管理する](m365bp-manage-windows-devices.md)
