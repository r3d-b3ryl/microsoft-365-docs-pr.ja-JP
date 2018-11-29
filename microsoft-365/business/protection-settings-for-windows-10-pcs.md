---
title: Windows 10 の PC のデバイス保護設定を設定する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: デフォルトおよびその他の設定を Windows 10 デバイスをセキュリティで保護する Microsoft 365 のビジネスで使用できるについて説明します。
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868995"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Windows 10 の PC のデバイス保護設定を設定する

## <a name="secure-windows-10-devices"></a>Windows 10 デバイスをセキュリティで保護する

Microsoft 365 Business で Windows 10 デバイスをセキュリティで保護する方法のビデオを表示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.office.com) にサインインします。 
    
2. 管理センターの [ **デバイス ポリシー**] カードで、[ **ポリシーの追加**] を選びます。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。
    
5. **セキュリティで保護された Windows の 10 のデバイス**を展開し\>どのようにしたい設定を構成します。詳細については、[利用可能な設定](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings)を参照してください。 
    
    [ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. 次に**にこれらの設定が表示されますか?** 既定**のすべてのユーザー**セキュリティ グループの選択の**変更**を使用したくない場合は、これらの設定が表示されますユーザー セキュリティ グループの検索\>**を選択**します。
    
7. 最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
    
## <a name="available-settings"></a>利用可能な設定

既定では、すべての設定が **オン**になっています。次の設定を使用できます。
  
詳細については、「[Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。 
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する  <br/> |インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。  <br/> |
|Microsoft Edge で Web ベースの脅威から PC を保護する  <br/> |ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。  <br/> |
|デバイスに対する攻撃を回避するルールを使用する  <br/> |オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](https://go.microsoft.com/fwlink/?linkid=870417)」を参照してください。  <br/> |
|ランサムウェアなどの脅威からフォルダーを保護する  <br/> |この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[フォルダーへのアクセス制御でフォルダーを保護する](https://go.microsoft.com/fwlink/?linkid=870418)」を参照してください。  <br/> |
|インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する  <br/> |この設定を使用すると、フィッシング詐欺、攻撃、またはその他の悪意のあるコンテンツをホストしている可能性がある低評価のインターネット上の場所へのユーザーの外部接続をブロックします。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[ネットワークを保護する](https://go.microsoft.com/fwlink/?linkid=870419)」を参照してください。  <br/> |
|不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する  <br/> |BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](https://go.microsoft.com/fwlink/?linkid=871000)」を参照してください。  <br/> |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  <br/> |ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  <br/> |
|ユーザーが Cortana にアクセスすることを許可する  <br/> |Cortana は非常に役に立つ場合があります。Cortana によって設定をオンまたはオフにしたり、手順を示したり、ユーザーが予定に間に合うようにしたりすることができるため、既定では、Microsoft はこの設定を **オン**にしています。  <br/> |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  <br/> |Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。  <br/> |
|Windows 10 デバイスを自動的に最新の状態に維持する  <br/> |Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。  <br/> |
|この時間アイドル状態になったときにデバイスの画面をオフにする  <br/> |ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーが、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりすると、デバイスを無作為な視線に向けて無防備な状態にしてしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。  <br/> |
   
  

