---
title: PC のデバイス保護設定を編集またはWindows 10する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: ビジネス向けアプリで使用できるMicrosoft 365デバイスをセキュリティで保護するWindows 10します。
ms.openlocfilehash: 1c1e510af4280233079961651ef8fe002d9bc3d6
ms.sourcegitcommit: 34259ec9b6cccc8f6e29808dbe4796d9f72b651b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2021
ms.locfileid: "59933293"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>PC のデバイス保護設定を編集またはWindows 10する

この記事は、このMicrosoft 365 Business Premium。

[セットアップ] ページで既定の Windows保護設定を設定した後、すべてのユーザーまたは一連のユーザーに適用される新しい保護設定を追加できます。 作成した任意のファイルを編集できます。

## <a name="create-protection-settings-for-windows-10-devices"></a>デバイスの保護設定をWindows 10する

次の方法でデバイスをセキュリティで保護するWindows 10ビデオをMicrosoft 365 Business Premium。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。 
2. 左側のナビゲーションで、[デバイス ポリシー **の** \> **追加] を** \> **選択します**。
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
4. [ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. 詳細については、「使用可能な設定 [」を参照してください](#available-settings)。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![[デバイス構成] が選択Windows 10ポリシー ウィンドウを追加します。](../../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 

## <a name="edit-windows-10-protection-settings"></a>保護Windows 10の編集
 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。     
2. 左側のナビゲーションで、[デバイス ポリシー **]** \> **を選択します** 。
1. 既存のデバイス ポリシーをWindowsし、[編集] を **クリックします**。
1. 変更 **する設定** の横にある [編集] を選択し、[保存] を **選択します**。

## <a name="available-settings"></a>利用可能な設定

既定では、すべての設定が **オン** になっています。次の設定を使用できます。
  
詳細については、「Intune の設定[にマップする方法Microsoft 365 プレミアム保護機能」を参照してください](map-protection-features-to-intune-settings.md)。 


|設定値  <br/> |説明  <br/> |
|:-----|:-----|
|Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  <br/> |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で PC を Web ベースの脅威から保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|デバイスに対する攻撃を回避するルールを使用する  <br/> |オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。  <br/> |
|ランサムウェアなどの脅威からフォルダーを保護する  <br/> |この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。 こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。 Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。 詳細 [については、「フォルダー アクセスの制御を使用してフォルダーを保護する」](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) を参照してください。  <br/> |
|インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する  <br/> |この設定を使用して、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある低評価のインターネットの場所への送信ユーザー接続をブロックします。 この設定は、[オン] に設定Windows Defender ウイルス対策場合にのみ使用 **できます**。 詳細については、「ネットワークを [保護する」を参照してください](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。 詳細については [、「Bitlocker FAQ」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)。  <br/> |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  <br/> |ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン** のままにしていますが、セキュリティを強化するためにオフにすることもできます。  <br/> |
|ユーザーが Cortana にアクセスすることを許可する  <br/> |Cortana は非常に役に立つ場合があります。 Cortanaの設定をオンまたはオフにしたり、指示を出したり、予定に間に合うのを確認したりすることができるので、この設定は既定で **オンのままに** します。  <br/> |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  <br/> |Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。  <br/> |
|Windows 10 デバイスを自動的に最新の状態に維持する  <br/> |Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |