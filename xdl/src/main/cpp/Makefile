all: build/arm64-v8a/libxdl.a


build/%/libxdl.a: CMakeLists.txt
	@mkdir -p $(@D)
	cmake \
		-B $(@D) \
		-DCMAKE_TOOLCHAIN_FILE=$(ANDROID_NDK_ROOT)/build/cmake/android.toolchain.cmake \
		-DANDROID_ABI=$* \
		-DANDROID_PLATFORM=android-30 \
		-DANDROID_STL=c++_static
	make -C $(@D)

clean:
	$(RM) -r build/

.PHONY: all clean
