---
title: Windows 10 の PC のデバイス保護設定を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
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
description: Windows 10 デバイスをセキュリティで保護するために Microsoft 365 for business で利用可能な既定の設定とその他の設定について説明します。
ms.openlocfilehash: 0403ea2c30221dd5693b7f3e9b4921ad175399a1
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402808"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Windows 10 の PC のデバイス保護設定を設定する

## <a name="secure-windows-10-devices"></a>Windows 10 デバイスをセキュリティで保護する

Microsoft 365 for business を使用して Windows 10 デバイスをセキュリティで保護する方法に関するビデオを参照してください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。 
    
2. 左側のナビゲーションで、[**デバイス**ポリシーの追加] を選択し \> **Policies** \> **Add**ます。
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。
    
5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. 詳細については、「[使用可能な設定](#available-settings)」を参照してください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.
    
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="available-settings"></a>利用可能な設定

既定では、すべての設定が **オン**になっています。 次の設定を使用できます。
  
詳細については、「 [Microsoft 365 Premium の保護機能を Intune 設定にマップする方法](map-protection-features-to-intune-settings.md)」を参照してください。 
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する  <br/> |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で PC を Web ベースの脅威から保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|デバイスに対する攻撃を回避するルールを使用する  <br/> |オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。  <br/> |
|ランサムウェアなどの脅威からフォルダーを保護する  <br/> |この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。 こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。 Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。 詳細については、「[フォルダーを制限付きフォルダーアクセスで保護](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)する」を参照してください。  <br/> |
|インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する  <br/> |この設定を使用して、フィッシング詐欺、悪用、またはその他の悪意のあるコンテンツをホストする可能性がある低評価のインターネット上の場所への送信ユーザー接続をブロックします。 この設定は、Windows Defender ウイルス対策が **[オン**] に設定されている場合にのみ使用できます。 詳細については、「[ネットワークを保護する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)」を参照してください。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。 詳細については、「Bitlocker に関する[FAQ](https://go.microsoft.com/fwlink/?linkid=871000)」を参照してください。  <br/> |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  <br/> |ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  <br/> |
|ユーザーが Cortana にアクセスすることを許可する  <br/> |Cortana は非常に役に立つ場合があります。 Cortana では、設定を有効または無効にしたり、案内を表示したり、予定に時間があるかどうかを確認したりすることができます。**この設定は既定でオンに**しておきます。  <br/> |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  <br/> |Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。  <br/> |
|Windows 10 デバイスを自動的に最新の状態に維持する  <br/> |Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |
