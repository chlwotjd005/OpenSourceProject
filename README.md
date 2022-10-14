
<span style="color:red">오픈소스 프로젝트 제안서입니다.</span>
==============================

1. ## 목표
  + GLTFast를 통한 Oculus Quest2(VR) 환경에서의 실시간 생성 3D Object의 저장 시스템 아키텍쳐 구축
2. ## 핵심내용
  + 현재 VR기기 중 바이브에서는 지원되나 Oculus Quest2에서는 지원되지 않는 실시간 생성 Object 저장 기능을 OpenSource 중 GLTFast를 활용해 Server에 저장하거나 불러올 수 있도록 한다.
* ## 예시코드
<pre>
<code>
async void LoadGltfBinaryFromMemory() {
    var filePath = "/path/to/file.glb";
    byte[] data = File.ReadAllBytes(filePath);
    var gltf = new GltfImport();
    bool success = await gltf.LoadGltfBinary(
        data, 
        // The URI of the original data is important for resolving relative URIs within the glTF
        new Uri(filePath)
        );
    if (success) {
        success = gltf.InstantiateMainScene(transform);
    }
}
</code>
</pre>

*****

* 참고 오픈소스 URL : <https://github.com/atteneder/glTFast/>


